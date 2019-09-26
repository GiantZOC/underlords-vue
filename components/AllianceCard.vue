<template>
  <v-card max-width="450px">
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
          <h3>{{title}}</h3>
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
        <v-list-item-content>{{bonus.description}}
          </v-list-item-content>        
      </v-list-item>
    </v-list>
    <v-card-text>
      <v-container fluid>
      <v-row>
        <v-col v-for="hero in heroes" :key="hero._id" cols="3" sm="4">
          <v-img
            :src="`~/static/images/portraits/npc_dota_hero_${hero.Filename}_png.png`"
            :srcset="require(`~/static/images/portraits/npc_dota_hero_${hero.Filename}_png.png`).srcSet"
            :lazy-src="require(`~/static/images/portraits/npc_dota_hero_${hero.Name.Filename}_png.png`).placeholder"
            
          ></v-img>
        </v-col>
      </v-row>
      </v-container>
    </v-card-text>
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
      Name: {
        type: String,
        required: true
      },
      Filename: {
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