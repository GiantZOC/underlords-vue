<template>
  <v-card>
    <NuxtLink :to="`../Hero/${name}`">
      <v-img
        class="hero_image"
        :src="require(`~/static${hero_image}`)"
        :srcset="require(`~/static${hero_image}`).srcSet"
        :lazy-src="require(`~/static${hero_image}`).placeholder"
      >
        <div class="title_blur">
          <v-card-title class="hero_title align-end fill-height" style="text-shadow: 0 1px 0 black;">
          <h3>{{name}} <v-avatar v-for="alliance in alliances" v-bind:key="alliance.name">
            <v-img
              :src="require(`~/static/images/alliances/${alliance.name.toLowerCase().replace(/\s/g, '')}.png`)"
              :srcset="require(`~/static/images/alliances/${alliance.name.toLowerCase().replace(/\s/g, '')}.png`).srcSet"
              :lazy-src="require(`~/static/images/alliances/${alliance.name.toLowerCase().replace(/\s/g, '')}.png`).placeholder"
            ></v-img>
          </v-avatar></h3>
        </v-card-title>
        </div>
      </v-img>
    </NuxtLink>
    <v-card v-for="ability in abilities" v-bind:key="ability.name" dark>
      <v-row>
          <v-col md="auto" class="pr-8">
            <div>
            <v-img
              class="hero_image float-xl-left px-4 mx-4"
              max-width="300px"
              min-width="150px"
              aspect-ratio="1"
              :src="require(`~/static${ability.ability_image}`)"
              :srcset="require(`~/static${ability.ability_image}`).srcSet"
              :lazy-src="require(`~/static${ability.ability_image}`).placeholder"
            ></v-img>
             <v-card-text class="pa-1 mx-4 title">
              <div>
                {{ability.ability}}
                
              </div>
            </v-card-text>
            <v-card-text class="pa-1 mx-4">
              {{ability.description}}
            </v-card-text>
            </div>
            <!-- <v-img
              max-width="300px"
              min-width="150px"
              aspect-ratio="1"
              :src="require(`~/static${round.image}`)"
              :srcset="require(`~/static${round.image}`).srcSet"
              :lazy-src="require(`~/static${round.image}`).placeholder"
            ></v-img> -->
          </v-col>
          <v-col md="auto">
           
            <!-- <v-card-text>{{round.quote}}</v-card-text> -->
          </v-col>
        </v-row>

      <!-- <v-list-item three-line>
        <v-list-item-avatar size="125" tile>
          <v-img
            class="hero_image"
            :src="require(`~/static${ability.ability_image}`)"
            :srcset="require(`~/static${ability.ability_image}`).srcSet"
            :lazy-src="require(`~/static${ability.ability_image}`).placeholder"
          ></v-img>
        </v-list-item-avatar>

        <v-list-item-content class="align-self-start">
          <v-list-item-title v-text="ability.ability" class="text--primary"></v-list-item-title>
          <v-list-item-subtitle v-text="ability.description" class="text--primary"></v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item> -->
    </v-card>
  </v-card>
</template>



<script>
export default {
  props: {
    _id: {
      type: String,
      required: true
    },
    alliances: {
      name: {
        type: String,
        required: true
      }
    },
    name: {
      type: String,
      required: true
    },
    hero_image: {
      type: String,
      required: true
    },
    abilities: {
      ability: {
        type: String,
        required: true
      },
      ability_image: {
        type: String,
        required: true
      },
      description: {
        type: String,
        required: true
      }
    }
  }
}
</script>

<style>
.title_blur {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  background: inherit;
  background-attachment: fixed;
  overflow: hidden;
}
.title_blur::before {
  content: '';
  position: absolute;
  top: -20px;
  left: 0;
  width: 200%;
  height: 200%;
  background: inherit;
  background-attachment: fixed;
  -webkit-filter: blur(4px);
  filter: blur(4px);
}
.title_blur::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
}
.title_blur > .hero_title > h3 {
  margin: 0;
  color: white;
  position: relative;
  z-index: 1;
}
</style>