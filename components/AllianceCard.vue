<template>
  <v-card max-width="450px">
    <v-list style="padding: 8px 0px 0px 0px">
      <v-list-item>
        
        <v-list-item-avatar>
          
          <v-img
            :src="require(`~/static/images/alliances/${name}.png`)"
            :srcset="require(`~/static/images/alliances/${name}.png`).srcSet"
            :lazy-src="require(`~/static/images/alliances/${name}.png`).placeholder"
            :alt=name
          ></v-img>
          
        </v-list-item-avatar>

        <v-list-item-content>
          <NuxtLink :to="`../Alliance/${name}`">
          <h3>{{title}}</h3>
          </NuxtLink>
        </v-list-item-content>
        
      </v-list-item>

      <v-list-item v-for="bonus in alliance_bonus" v-bind:key="bonus.unit_count + name">
        <div class="AllianceCard_UnitCountContainer">
          <!-- Filled in Boxes -->
          <div
            v-for="n in bonus.unit_count"
            v-bind:key="n + bonus.unit_count"
            class="AllianceCard_Unit"
            v-bind:style="{ backgroundColor: color, height: height}"
          ></div>
          <!-- Empty Boxes -->
          <div
            v-for="n in alliance_max_bonus_count-bonus.unit_count"
            v-bind:key="n + 'max'"
            class="AllianceCard_Unit"
            v-bind:style="{ height: height}"
          ></div>
        </div>
        <v-list-item-content>{{bonus.description}}
          </v-list-item-content>        
      </v-list-item>
    </v-list>
      <v-container fluid>
      <v-row>
        <v-col v-for="hero in heroes" :key="hero._id" cols="3" sm="4">
          <NuxtLink :to="`/Hero/${hero.name}`">
          <v-img
            :src="`~/static/images/portraits/npc_dota_hero_${hero.filename}_png.png`"
            :srcset="require(`~/static/images/portraits/npc_dota_hero_${hero.filename}_png.png`).srcSet"
            :lazy-src="require(`~/static/images/portraits/npc_dota_hero_${hero.filename}_png.png`).placeholder"
            :alt=hero.name
          ></v-img>
          </NuxtLink>
        </v-col>
      </v-row>
      </v-container>
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
    heroes: {
      _id:{
        type: String,
        required: true
      },
      name: {
        type: String,
        required: true
      },
      filename: {
        type: String,
        required: true
      }
    },
    alliance_max_bonus_count: {
      //2, 4, 6
      type: Number,
      required: true
    },
    alliance_bonus:{
      unit_count: {
        type: Number,
        required: true
      },
      description: {
        type: String,
        required: true
      }
    },
    height: {
      type: String,
      required: true
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
</style>