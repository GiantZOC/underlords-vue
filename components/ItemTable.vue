<template>
  <div>
    <v-select
    style="max-width: 200px"
      v-model="selectedTier"
      :items="tiers"
      label="Filter by Tier"
    ></v-select>
    <div v-if="$apollo.loading">Loading...</div>
    <!-- prepend-inner-icon="Tier" -->
    <v-data-table
      :headers="itemsheader"
      :items="filteredItems"
      sort-by="tier"
      class="elevation-1"
      :disable-pagination="true"
      :hide-default-footer="true"
    >
      <!-- custom item formatting -->
      <template v-slot:item.img="{ item }">
        <NuxtLink :to="`Item/${item._id}`">
        <v-avatar>
          <v-img
            :src="require(`~/static${item.img}`)"
            :srcset="require(`~/static${item.img}`).srcSet"
            :lazy-src="require(`~/static${item.img}`).placeholder"
          >
          </v-img>
        </v-avatar>
         </NuxtLink>
      </template> 
    </v-data-table>
  </div>
</template>
<script>
import getItems from '~/apollo/queries/getItems'

export default {
  name: 'ItemTable',
  data() {
    return {
      selectedTier: '',
      tiers: ['', '1', '2', '3', '4', '5'],
      itemsheader: [
        {
          text: '',
          align: 'left',
          sortable: false,
          value: 'img'
        },
        {
          text: 'Name',
          align: 'left',
          sortable: true,
          value: 'name'
        },
        {
          text: 'Description',
          align: 'left',
          sortable: true,
          value: 'description'
        },
        {
          text: 'Tier',
          align: 'left',
          sortable: true,
          value: 'tier',
          width: '70px'
        },
        {
          text: 'Type',
          align: 'left',
          sortable: true,
          value: 'type'
        },
        {
          text: 'Flavor',
          align: 'left',
          sortable: false,
          value: 'flavortext'
        }
      ],
      items: []
    }
  },
  apollo: {
    items: {
      query: getItems
    }
  },
  computed: {
    // https://stackoverflow.com/questions/45672145/how-do-i-use-custom-filter-prop-in-data-tables-in-vuetify-or-how-do-i-create
    filteredItems() {
      return this.items.filter(i => {
        return (
          this.selectedTier == '' || i.tier.toString() === this.selectedTier
        )
      })
    }
  }
}
</script>
<style scoped>
.v-avatar {
  border-radius: 0px;
}
</style>