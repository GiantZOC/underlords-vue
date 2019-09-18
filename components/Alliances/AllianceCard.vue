<template>
  <v-card>
    <v-list>
      <v-list-item>
        <v-list-item-avatar>
          <v-img
            :src="require(`~/static/images/alliances/${name}.png`)"
            :srcset="require(`~/static/images/alliances/${name}.png`).srcSet"
            :lazy-src="require(`~/static/images/alliances/${name}.png`).placeholder"
          ></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <h1>{{title}}</h1>
        </v-list-item-content>
      </v-list-item>

      <v-list-item v-for="bonus in alliance_bonus" v-bind:key="bonus.unit_count">
        <div class="AllianceCard_UnitCountContainer">
          <!-- Filled in Boxes -->
          <div
            v-for="unit in bonus.unit_count"
            v-bind:key="unit"
            class="AllianceCard_Unit"
            v-bind:style="{ backgroundColor: color, height: height}"
          ></div>
          <!-- Empty Boxes -->
          <div
            v-for="n in alliance_max_bonus_count-bonus.unit_count"
            v-bind:key="n"
            class="AllianceCard_Unit"
            v-bind:style="{ height: height}"
          ></div>
        </div>
        {{bonus.description}}
      </v-list-item>
    </v-list>
    <v-card-text>
      <v-container fluid>
      <v-row>
        <v-col v-for="unit in unit_names" :key="unit" cols="3" sm="4">
          <v-img
            :src="`~/static/images/portraits/npc_dota_hero_${unit}_png.png`"
            :srcset="require(`~/static/images/portraits/npc_dota_hero_${unit}_png.png`).srcSet"
            :lazy-src="require(`~/static/images/portraits/npc_dota_hero_${unit}_png.png`).placeholder"
            
          ></v-img>
        </v-col>
      </v-row>
      </v-container>
    </v-card-text>
    <!-- <v-list>
      <v-list-item>
        <v-list-item-avatar height="80px" width="80px" v-for="unit in unit_names" v-bind:key="unit">
          
        </v-list-item-avatar>
      </v-list-item>
    </v-list>-->
  </v-card>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    color: {
      type: String,
      required: true
    },
    unit_names: [String],
    alliance_max_bonus_count: {
      //2, 4, 6
      type: Number,
      required: true
    },
    alliance_bonus: [Object],
    height: {
      type: String,
      required: true
    }
  }
}
</script>