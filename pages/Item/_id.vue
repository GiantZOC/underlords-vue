<template>
  <div v-if="Item">
    <v-card>
      <v-row>
        <v-col md="auto">
          <v-img
            :max-width="imageWidth"
            :src="require(`~/static${Item.img}`)"
            :srcset="require(`~/static${Item.img}`).srcSet"
            :lazy-src="require(`~/static${Item.img}`).placeholder"
          ></v-img>
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <v-list>
            <v-list-item>
              <v-list-item-content>
                <h3>{{Item.name}}</h3>
              </v-list-item-content>
            </v-list-item>
            <v-list-item>
              <v-list-item-content>Description: {{Item.description}}</v-list-item-content>
            </v-list-item>
            <v-list-item>
              <v-list-item-content>Tier: {{Item.tier}}</v-list-item-content>
            </v-list-item>
            <v-list-item>
              <v-list-item-content>Type: {{Item.type}}</v-list-item-content>
            </v-list-item>
            <v-list-item>
              <v-list-item-content><div class="font-italic">{{Item.flavortext}}</div></v-list-item-content>
            </v-list-item>
          </v-list>
          <v-card-text></v-card-text>
        </v-col>
      </v-row>
    </v-card>
  </div>
</template>

<script>
import getItem from '~/apollo/queries/getItem'
export default {
  apollo: {
    Item: {
      query: getItem,
      prefetch: ({ route }) => ({ itemId: route.params.id }),
      variables() {
        return { itemId: this.$route.params.id }
      }
    }
  },
  head() {
    return {
      title: this.Item ? `${this.Item.name}` : 'Loading'
    }
  },
  computed: {
      imageWidth () {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs': return '150px'
          case 'sm': return '225px'
          case 'md': return '300px'
          case 'lg': return '300px'
          case 'xl': return '300px'
        }
      },
    },
}
</script>