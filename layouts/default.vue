<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-btn
        icon
        @click.stop="clipped = !clipped"
      >
        <v-icon>mdi-application</v-icon>
      </v-btn>
      <v-btn
        icon
        @click.stop="fixed = !fixed"
      >
        <v-icon>mdi-minus</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn
        icon
        @click.stop="rightDrawer = !rightDrawer"
      >
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
    >
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light>
              mdi-repeat
            </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-footer
      :fixed="fixed"
      app
    >
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
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
          title: 'Loot Table',
          to: '/LootTable'
        }
        
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>

<style>

.AllianceCard_UnitCountContainer {
    display: inline-flex;
    flex-direction: column;
    flex-wrap: wrap;
    height: 40px;
    align-content: flex-start;
    width: 20%;
    vertical-align: middle;
    margin:5px
  }
  
  .AllianceCard_Unit {
    box-sizing: border-box;
    height: 45%;
    width: 10px;
    border: 1px solid grey;
    margin: 1px;
    border-radius: 3px;
  
  }
  
  .AllianceCard_Effect {
    display: inline-block;
    width: 80%;
    vertical-align: middle;
  }
  
  .v-avatar {
    border-radius: 0px;
  }

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
