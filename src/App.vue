<template>
  <v-app :light="!dark" :dark="dark">
    <v-toolbar fixed>
      <v-toolbar-title v-text="title"></v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn v-if="dynamic" icon v-for="(theme, index) in themes" :key="index" @click.native="setTheme(theme)">
        <theme-icon :colors="theme"></theme-icon>
      </v-btn>

      <v-btn icon @click.native="dark = !dark">
        <v-icon v-html="dark ? 'lightbulb_outline' : 'wb_incandescent'"></v-icon>
      </v-btn>
    </v-toolbar>
    <main>
      <v-container fluid grid-list-lg>
        <v-layout row wrap>
          <v-flex xs12 sm12 md12>
            <v-card>
              <blockquote>
                This is test of dynamic CSS variables usage in <a href="https://vuetifyjs.com">Vuetify</a>. Source code available on <a
                href="https://github.com/darosh/vuetifyjs-dynamic-theme-example">GitHub</a>.
                <span v-if="dynamic">Click toolbar buttons to switch theme.</span>
                <b v-if="!dynamic">Open this page in a better browser to switch theme.</b>
              </blockquote>
            </v-card>
          </v-flex>
          <v-flex xs12 sm6 md4>
            <v-card>
              <v-card-title primary-title>
                <div class="title">Checkboxes</div>
              </v-card-title>
              <v-divider></v-divider>
              <v-layout row wrap ml-3>
                <v-checkbox label="Primary"
                            v-model="checkbox"
                            color="primary"
                            :value="1"
                            hide-details></v-checkbox>
                <v-checkbox label="Secondary"
                            v-model="checkbox"
                            color="secondary"
                            :value="1"
                            hide-details></v-checkbox>
                <v-checkbox label="Accent"
                            v-model="checkbox"
                            color="accent"
                            :value="1"
                            hide-details></v-checkbox>
              </v-layout>
            </v-card>
          </v-flex>
          <v-flex xs12 sm6 md4>
            <v-card>
              <v-card-title primary-title>
                <div class="title">Switches</div>
              </v-card-title>
              <v-divider></v-divider>
              <v-layout row wrap ml-3>
                <v-switch label="Primary"
                          v-model="switches"
                          color="primary"
                          :value="1"
                          hide-details></v-switch>
                <v-switch label="Secondary"
                          v-model="switches"
                          color="secondary"
                          :value="1"
                          hide-details></v-switch>
                <v-switch label="Accent"
                          v-model="switches"
                          color="accent"
                          :value="1"
                          hide-details></v-switch>
              </v-layout>
            </v-card>
          </v-flex>
          <v-flex xs12 sm6 md4>
            <v-card>
              <v-card-title primary-title>
                <div class="title">Radios</div>
              </v-card-title>
              <v-divider></v-divider>
              <v-layout row wrap ml-3>
                <v-radio label="Primary"
                         v-model="radio"
                         color="primary"
                         :value="1"
                         hide-details></v-radio>
                <v-radio label="Secondary"
                         v-model="radio"
                         color="secondary"
                         :value="1"
                         hide-details></v-radio>
                <v-radio label="Accent"
                         v-model="radio"
                         color="accent"
                         :value="1"
                         hide-details></v-radio>
              </v-layout>
            </v-card>
          </v-flex>
          <v-flex xs12 sm6 md4>
            <v-card>
              <v-card-title primary-title>
                <div class="title">Buttons</div>
              </v-card-title>
              <v-divider></v-divider>
              <div pa>
                <buttons-1></buttons-1>
                <buttons-2></buttons-2>
              </div>
            </v-card>
          </v-flex>
          <v-flex xs12 sm6 md4>
            <v-card>
              <v-card-title primary-title>
                <div class="title">Progress</div>
              </v-card-title>
              <v-divider></v-divider>
              <div pa>
                <progress-circular-3></progress-circular-3>
              </div>
            </v-card>
          </v-flex>
          <v-flex xs12 sm6 md4>
            <v-card>
              <v-card-title primary-title>
                <div class="title">Tabs</div>
              </v-card-title>
              <v-divider></v-divider>
              <tabs-1></tabs-1>
            </v-card>
          </v-flex>
          <v-flex xs12 sm6 md4>
            <v-card>
              <v-card-title primary-title>
                <div class="title">Badges</div>
              </v-card-title>
              <v-divider></v-divider>
              <div pa>
                <badges-3></badges-3>
              </div>
            </v-card>
          </v-flex>
          <v-flex xs12 sm6 md4>
            <v-card>
              <v-card-title primary-title>
                <div class="title">Chips</div>
              </v-card-title>
              <v-divider></v-divider>
              <div pa>
                <chips-3></chips-3>
              </div>
            </v-card>
          </v-flex>
          <v-flex xs12 sm6 md4>
            <v-card>
              <v-card-title primary-title>
                <div class="title">Slider</div>
              </v-card-title>
              <v-divider></v-divider>
              <div pa style="padding-bottom: 0; padding-top: 10px;">
                <v-slider value="50"></v-slider>
              </div>
            </v-card>
          </v-flex>
          <v-flex xs12 sm6 md4>
            <v-card>
              <v-card-title primary-title>
                <div class="title">Cards</div>
              </v-card-title>
              <v-divider></v-divider>
              <cards-3></cards-3>
            </v-card>
          </v-flex>
          <v-flex xs12 sm6 md4>
            <v-card>
              <v-card-title primary-title>
                <div class="title">Picker</div>
              </v-card-title>
              <v-divider></v-divider>
              <div>
                <v-date-picker landscape v-model="date"></v-date-picker>
              </div>
            </v-card>
          </v-flex>
          <v-flex xs12 sm6 md4>
            <v-card>
              <v-card-title primary-title>
                <div class="title">Toolbars</div>
              </v-card-title>
              <v-divider></v-divider>
              <toolbar-2></toolbar-2>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
    </main>
  </v-app>
</template>

<script>
  let CSS_VARIABLES = false

  // Feature detection
  if ((window.CSS && window.CSS.supports && window.CSS.supports('--fake-var', 0)) &&
    // Browser detection: Edge browser has bugs in some components
    !(window.navigator.userAgent.indexOf('Edge') > -1)) {
    CSS_VARIABLES = true
    // import('./stylus/main.stylus')
  } else {
    import('./stylus/main.compatibility.stylus')
  }

  export default {
    components: {
      'theme-icon': () => import('./components/ThemeIcon.vue'),
      'toolbar-2': () => import('./components/docs/examples/toolbar/2.vue'),
      'buttons-1': () => import('./components/docs/examples/buttons/1.vue'),
      'buttons-2': () => import('./components/docs/examples/buttons/2.vue'),
      'cards-3': () => import('./components/docs/examples/cards/3.vue'),
      'progress-circular-3': () => import('./components/docs/examples/progress-circular/3.vue'),
      'chips-3': () => import('./components/docs/examples/chips/3.vue'),
      'badges-3': () => import('./components/docs/examples/badges/3.vue'),
      'tabs-1': () => import('./components/docs/examples/tabs/1.vue')
    },
    data () {
      return {
        title: 'Vuetify Dynamic Themes',
        dark: false,
        themes: [
          ['#00796b', '#ffab40', '#e0e0e0'],
          ['#3f51b5', '#f50057', '#4fc3f7'],
          ['#f50057', '#4fc3f7', '#3f51b5'],
          ['#ffc400', '#9e9e9e', '#1976d2'],
          ['#1976d2', '#ffc400', '#9e9e9e']
        ],
        date: null,
        checkbox: 1,
        radio: 1,
        switches: 1,
        dynamic: CSS_VARIABLES
      }
    },
    methods: {
      setTheme (theme) {
        document.body.style.setProperty('--primary', theme[0])
        document.body.style.setProperty('--accent', theme[1])
        document.body.style.setProperty('--secondary', theme[2])
      }
    }
  }
</script>

<style lang="stylus">
  @import './stylus/main.stylus'

  [pa] {
    padding: 16px
  }
</style>
