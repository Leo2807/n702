<template>
  <div id="app">
    <main>
      <h1>N702</h1>
      <p>Dit document bespreekt de ontwikkeling van de N702 tussen het Kolonel Dusartplein en de R71 tussen 1971 en 2017.</p>
      <evolution v-for="evolution in evolutions" v-bind="evolution" />
    </main>
    <footer>
      Foto's: ©2017 <a href=https://www.geopunt.be>www.geopunt.be</a>
    </footer>
  </div>
</template>

<script>

import Evolution from './components/Evolution.vue'

export default {
  name: 'app',
  components: {
    Evolution
  },
  data () {
    return {
      swiperOptions: {
        followFinger: false,
        allowTouchMove: false,
        resistanceRatio: 1,

        navigation: {
          nextEl: '.next',
          prevEl: '.prev'
        }
      },
      evolutions: [
        {
          from: '2017',
          to: '1971',
          text: 'In 1971 zie je dat de N702 nog niet doorgetrokken was. Daarnaast is het Kapermolenpark nog niet aangelegd en is er weinig bebouwing langs de R71.',
          title: '1971'
        },
        {
          from: '1971',
          to: '1979-1990',
          text: 'In de jaren ‘80 is de N702 al doorgetrokken naar de kleine ring, de R70, die toen nog een 2×2-rijstrookconfiguratie had. Men is ook al begonnen aan de grenslandhallen. Het kapermolenpark en -zwembad zijn ook al aangelegd. Tot slot is er ook meer bebouwing aan de buitenkant van de grote ring.',
          title: '1979-1990'
        },
        {
          from: '1979-1990',
          to: '2000-2003',
          title: '2000-2003',
          text: 'Tegen 2000-2003 zijn de grenslandhallen met één gebouw uitgebreid, is de Japanse tuin ook aangelegd. Op de foto kan je het niet goed zien, maar de kleine ring is omgebouwd tot een eenrichtingsstraat met twee rijstroken.'
        },
        {
          from: '2000-2003',
          to: '2017',
          title: '2017',
          text: 'Tegen 2017 zijn de grenslandhallen uitgebreid met de Ethiasarena en Plopsaland. De N702 wordt nu voor de helft als parkeerstrook gebruikt waardoor er nog een 2×1-weg overblijft. Het Kapermolenzwembad is verkleind, en op de vrijgekomen plaats is nu een bouwwerf aanwezig.'
        }
      ].map((ev) => {
        return {
          ...ev,
          from: require('./assets/geopunt/Geopunt Vlaanderen ' + ev.from + '.png'),
          to: require('./assets/geopunt/Geopunt Vlaanderen ' + ev.to + '.png')
        }
      })
    }
  }
}
</script>

<style>
body {
  margin: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

main {
  text-align: center;
  margin-top: 40px;
  max-width: 50rem;
  margin: auto;
}

footer {
  text-align: center;
  background: #2c3e50;
  padding: 2rem;
  color: #4DBA87;
}

</style>
