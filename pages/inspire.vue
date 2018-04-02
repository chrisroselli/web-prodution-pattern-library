<template>
  <v-layout>
    <v-flex sm12>
      <v-card>
        <v-tabs v-model="active" color="brown darken-2" dark slider-color="light-green darken-2">
          <v-tab>
            HTML
          </v-tab>
          <v-tab-item>
            <v-card color="light-green lighten-4">
              <v-card-text>
                <pre v-highlightjs="html">
                    <code class="html">
                    </code>
                  </pre>
              </v-card-text>
            </v-card>
          </v-tab-item>
          <v-tab>
            CSS
          </v-tab>
          <v-tab-item>
            <v-card color="light-green lighten-4">
              <v-card-text>
                <pre v-highlightjs="css">
                    <code class="css">
                    </code>
                  </pre>
              </v-card-text>
            </v-card>
          </v-tab-item>
          <v-tab>
            JS
          </v-tab>
          <v-tab-item>
            <v-card color="light-green lighten-4">
              <v-card-text>
                <pre v-highlightjs="js">
                    <code class="js">
                    </code>
                  </pre>
              </v-card-text>
            </v-card>
          </v-tab-item>
        </v-tabs>
      <v-layout pa-5 row justify-space-between>
      <v-flex xs6>

      </v-flex>
      <v-flex xs8>
     <span v-html="component"></span>
  
      </v-flex>
      <v-flex xs6>

      </v-flex>
    </v-layout>

            


      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
  import VueHighlightJS from "vue-highlightjs";
  import "highlight.js/styles/atom-one-dark.css";
  export default {
    data() {
      return {
        active: null,
        html: '<a class="cta-button" href="/free-estimate.html">Schedule A Free Estimate</a>',
        css: `.cta-button {
                display: inline-block;
                background-color: #353535;
                text-transform: uppercase;
                padding: 1rem 2rem 1.0625rem 2rem;
                color: #fff;
                font-size: 20px;
                font-weight: bold;
                position: relative;
                bottom: 5px;
                transition: all 0.4s ease 0s;
                  }`,
        js: "",
        component: `
                <style>
                  .cta-button {
                    display: inline-block;
                    background-color: #353535;
                    text-transform: uppercase;
                    padding: 1rem 2rem 1.0625rem 2rem;
                    color: #fff;
                    font-size: 20px;
                    font-weight: bold;
                    position: relative;
                    bottom: 5px;
                    transition: all 0.4s ease 0s;
                    text-decoration: none;
                  }
                </style>
            <a class="cta-button" href="/free-estimate.html">Schedule A Free Estimate</a>
            `
      };
    },
    methods: {
      next() {
        const active = parseInt(this.active);
        this.active = (active < 2 ? active + 1 : 0).toString();
      }
    }
  };
</script>