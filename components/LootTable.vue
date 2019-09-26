<template>
  <div>
    <v-banner>
      <v-avatar
      slot="icon"
      size="30"
      style="margin-right:0px"
    >
        <v-img
          :src="require(`~/static/images/yo.png`)"
          :srcset="require(`~/static/images/yo.png`).srcSet"
          :lazy-src="require(`~/static/images/yo.png`).placeholder"
        ></v-img>
      </v-avatar>Losing to a neutral creep wave results in being offered rewards from the previous creep wave's tier (Losing to the first creep wave has no penalty)
    </v-banner>

    <v-data-table
      :headers="loottableheader"
      :items="loottable"
      class="elevation-1"
      dense
      disable-pagination=true
      hide-default-footer=true
    ></v-data-table>
  </div>
</template>

<script>
export default {
  name: 'LootTable',
  data() {
    return {
      loottableheader: [
        {
          text: 'Round',
          align: 'left',
          sortable: true,
          value: 'Round'
        },
        {
          text: 'Tier 1',
          align: 'left',
          sortable: false,
          value: 'Tier1'
        },
        ,
        {
          text: 'Tier 2',
          align: 'left',
          sortable: false,
          value: 'Tier2'
        },
        {
          text: 'Tier 3',
          align: 'left',
          sortable: false,
          value: 'Tier3'
        },
        {
          text: 'Tier 4',
          align: 'left',
          sortable: false,
          value: 'Tier4'
        },
        {
          text: 'Tier 5',
          align: 'left',
          sortable: false,
          value: 'Tier5'
        }
      ],
      loottable: [
        {
          Round: 1,
          Tier1: 100,
          Tier2: 0,
          Tier3: 0,
          Tier4: 0,
          Tier5: 0
        },
        {
          Round: 2,
          Tier1: 80,
          Tier2: 20,
          Tier3: 0,
          Tier4: 0,
          Tier5: 0
        },
        {
          Round: 3,
          Tier1: 70,
          Tier2: 30,
          Tier3: 0,
          Tier4: 0,
          Tier5: 0
        },
        {
          Round: 10,
          Tier1: 20,
          Tier2: 80,
          Tier3: 0,
          Tier4: 0,
          Tier5: 0
        },
        {
          Round: 15,
          Tier1: 0,
          Tier2: 70,
          Tier3: 30,
          Tier4: 0,
          Tier5: 0
        },
        {
          Round: 20,
          Tier1: 0,
          Tier2: 30,
          Tier3: 70,
          Tier4: 0,
          Tier5: 0
        },
        {
          Round: 25,
          Tier1: 0,
          Tier2: 0,
          Tier3: 70,
          Tier4: 30,
          Tier5: 0
        },
        {
          Round: 30,
          Tier1: 0,
          Tier2: 0,
          Tier3: 50,
          Tier4: 50,
          Tier5: 0
        },
        {
          Round: 35,
          Tier1: 0,
          Tier2: 0,
          Tier3: 20,
          Tier4: 80,
          Tier5: 0
        },
        {
          Round: 40,
          Tier1: 0,
          Tier2: 0,
          Tier3: 0,
          Tier4: 70,
          Tier5: 30
        },
        {
          Round: 45,
          Tier1: 0,
          Tier2: 0,
          Tier3: 0,
          Tier4: 50,
          Tier5: 50
        },
        {
          Round: 50,
          Tier1: 0,
          Tier2: 0,
          Tier3: 0,
          Tier4: 40,
          Tier5: 60
        }
      ]
    }
  }
}
</script>

<style>
div.v-avatar.v-banner__icon {
    margin-right: 0px;
}
</style>