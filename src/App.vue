<template>
  <AppHeader></AppHeader>
  <div v-for="house in houses">blep</div>
  <main>
    <!-- ======= Intro ======= -->
    <section class="c-intro">
      <div class="container">
        <div class="row">
          <div class="col-12">
            <div class="c-intro__border">
              <h1 class="c-intro__title">Panden te koop</h1>
              <span class="u-color-text">De Panne en omgeving</span>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- End Intro -->

    <!-- ======= Property Grid ======= -->
    <section>
      <div class="container">
        <div class="row">
          <div class="c-loader">
            <div class="c-loader__bar"></div>
            <div class="c-loader__bar"></div>
            <div class="c-loader__bar"></div>
          </div>
          <!-- Start voorbeeld: 1 pand -->
          <div class="col-md-4">
            <div class="c-pand">
              <div class="c-pand__img">
                <img src="img/property-1.jpg" alt="" class="c-pand__img img-fluid" />
              </div>
              <div class="c-pand__overlay">
                <div class="c-pand__content">
                  <div class="c-pand__header">
                    <h2 class="c-pand__title">Villa Emma</h2>
                    Leopold I Esplanade 1/3<br />
                    8660 De Panne
                  </div>
                  <div class="c-pand__body">
                    <div class="pb-1 d-flex">
                      <span class="c-pand__price">&euro; 395.000</span>
                    </div>
                  </div>
                  <div class="c-pand__footer">
                    <ul class="c-pand__info d-flex justify-content-around">
                      <li>
                        <h4 class="c-pand__label">Opp</h4>
                        <span>340m<sup>2</sup></span>
                      </li>
                      <li>
                        <h4 class="c-pand__label">Slpks</h4>
                        <span>2</span>
                      </li>
                      <li>
                        <h4 class="c-pand__label">Badk</h4>
                        <span>4</span>
                      </li>
                      <li>
                        <h4 class="c-pand__label">Garage</h4>
                        <span>Ja</span>
                      </li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <!-- End voorbeeld: 1 pand -->
        </div>
      </div>
    </section>
    <!-- End Property Grid -->
  </main>
  <AppFooter></AppFooter>
</template>

<script setup>
import AppHeader from './components/AppHeader.vue';
import AppFooter from './components/AppFooter.vue';
import { ref } from 'vue';

const houses = ref();
const getHouses = async function () {
  const data = await fetch(`https://realestate-api.fgmnts.be/api/v1/homes/?nopagination=true`).then((r) => r.json());
  console.warning('work');

  houses.value = data;
  console.log(pokemons.value);
};

getHouses();
</script>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
