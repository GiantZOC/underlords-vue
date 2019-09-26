<template>

  <v-card>
    <NuxtLink :to="`Hero/${_id}`">
    <v-img
      class="hero_image"
      :src="require(`~/static${Hero_Image}`)"
      :srcset="require(`~/static${Hero_Image}`).srcSet"
      :lazy-src="require(`~/static${Hero_Image}`).placeholder"
    >
      <div class="title_blur">
        <v-card-title class="hero_title align-end fill-height" style="text-shadow: 0 1px 0 black;">
          <h3>{{Name}} <v-avatar v-for="alliance in Alliances" v-bind:key="alliance">
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
    <v-card v-for="Ability in Abilities" v-bind:key="Ability.Name" dark>
      <v-list-item three-line>
        <v-list-item-avatar size="125" tile>
          <v-img
            class="hero_image"
            :src="require(`~/static${Ability.Ability_Image}`)"
            :srcset="require(`~/static${Ability.Ability_Image}`).srcSet"
            :lazy-src="require(`~/static${Ability.Ability_Image}`).placeholder"
          ></v-img>
        </v-list-item-avatar>

        <v-list-item-content class="align-self-start">
          <v-list-item-title v-text="Ability.Ability" class="text--primary"></v-list-item-title>
          <v-list-item-subtitle v-text="Ability.Description" class="text--primary"></v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
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
    Alliances:{
      name:{
        type: String,
        required: true
      }
    },
    Name: {
      type: String,
      required: true
    },
    Hero_Image: {
      type: String,
      required: true
    },
    Abilities:{
      Ability: {
        type: String,
        required: true
      },
      Ability_Image: {
        type: String,
        required: true
      },
      Description: {
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