<template>
  <v-app dark>
    <v-img class="background"
        :src="require(`~/static/images/background.jpg`)"
        :srcset="require(`~/static/images/background.jpg`).srcSet"
        :lazy-src="require(`~/static/images/background.jpg`).placeholder"
      >
    <v-navigation-drawer class="visible-background" v-model="drawer" :mini-variant="miniVariant" :clipped="clipped" fixed app>
      <v-list>
        <v-list-item v-for="(item, i) in items" :key="i" :to="item.to" router exact>
          <v-list-item-action>
            <v-icon large>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title class="font-weight-bold" v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar class="visible-background" :clipped-left="clipped" app>
      <v-app-bar-nav-icon x-large @click.stop="drawer = !drawer" />
      <div class="container">
      <div class="d-flex justify-center align-center">
      <NuxtLink class="" :to="'/'">
      <v-avatar tile class="ml-4">
      <v-img
        :src="require(`~/static/images/underlords_icon_white.png`)"
        :srcset="require(`~/static/images/underlords_icon_white.png`).srcSet"
        :lazy-src="require(`~/static/images/underlords_icon_white.png`).placeholder"
      ></v-img>
      </v-avatar>
      </NuxtLink>
      <NuxtLink :to="'/'" style="color: inherit; text-decoration: none;">
      <v-toolbar-title  class="font-weight-bold headline pl-2" v-text="title" />
      </NuxtLink>
      </div>
      </div>
    </v-app-bar>
    <v-content>
      
      <v-container>
        <nuxt />
      </v-container>
      
    </v-content>

    <v-footer :fixed="fixed" app :absolute="true" inset>
      <span class="caption">
        Game content and materials are trademarks and copyrights of their respective publisher and its licensors. All rights reserved.
        This site is not affiliated with the game publisher.
      </span>
    </v-footer>
    </v-img>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: true,
      drawer: true,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-account-group',
          title: 'Alliances',
          to: '/Alliances'
        },
        {
          icon: 'mdi-account',
          title: 'Heroes',
          to: '/Heroes'
        },
        {
          icon: 'mdi-treasure-chest',
          title: 'Items',
          to: '/Items'
        },
        {
          icon: 'mdi-dice-6',
          title: 'Loot Rounds',
          to: '/LootTable'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Underlords Stats'
    }
  }
}
</script>


<style>

.visible-background{
  opacity: .9
}

.background {
  
  /* Background image is centered vertically and horizontally at all times */
  background-position: center center;
  
  /* Background image doesn't tile */
  background-repeat: no-repeat;
  
  /* Background image is fixed in the viewport so that it doesn't move when 
     the content's height is greater than the image's height */
  background-attachment: fixed;
  
  /* This is what makes the background image rescale based
     on the container's size */
  background-size: cover;
  
  /* Set a background color that will be displayed
     while the background image is loading */
  background-color: #464646;
}
</style>
