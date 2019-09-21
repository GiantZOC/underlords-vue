<template>
  <v-card>
    <v-img
      class="hero_image"
      :src="require(`~/static${Hero_Image}`)"
      :srcset="require(`~/static${Hero_Image}`).srcSet"
      :lazy-src="require(`~/static${Hero_Image}`).placeholder"
    >
      <div class="title_blur">
        <v-card-title class="hero_title align-end fill-height" style="text-shadow: 0 1px 0 black;">
          <h3>{{Name}}</h3>
        </v-card-title>
      </div>
    </v-img>

    <v-card-text>
      <v-simple-table dense>
        <template v-slot:default>
          <thead>
            <tr>
              <th class="text-left">Tier</th>
              <th class="text-left">Star 1</th>
              <th class="text-left">Star 2</th>
              <th class="text-left">Star 3</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>Health</td>
              <td>{{Tier_1_Health}}</td>
              <td>{{Tier_2_Health}}</td>
              <td>{{Tier_3_Health}}</td>
            </tr>
            <tr>
              <td>Mana</td>
              <td>{{Mana}}</td>
              <td>{{Mana}}</td>
              <td>{{Mana}}</td>
            </tr>
            <tr>
              <td>DPS</td>
              <td>{{Tier_1_DPS}}</td>
              <td>{{Tier_2_DPS}}</td>
              <td>{{Tier_3_DPS}}</td>
            </tr>
            <tr>
              <td>Damage</td>
              <td>{{Tier_1_AD_MIN}}/{{Tier_1_AD_Max}}</td>
              <td>{{Tier_2_AD_MIN}}/{{Tier_2_AD_Max}}</td>
              <td>{{Tier_3_AD_MIN}}/{{Tier_3_AD_Max}}</td>
            </tr>
            <tr>
              <td>Attack Speed</td>
              <td>{{Tier_1_Attack_Rate}}</td>
              <td>{{Tier_1_Attack_Rate}}</td>
              <td>{{Tier_1_Attack_Rate}}</td>
            </tr>
            <tr>
              <td>Move Speed</td>
              <td>{{Move_Speed}}</td>
              <td>{{Move_Speed}}</td>
              <td>{{Move_Speed}}</td>
            </tr>
            <tr>
              <td>Attack Range</td>
              <td>{{Attack_Range}}</td>
              <td>{{Attack_Range}}</td>
              <td>{{Attack_Range}}</td>
            </tr>
            <tr>
              <td>Magic Resist</td>
              <td>{{Tier_1_Magic_Resist}}</td>
              <td>{{Tier_2_Magic_Resist}}</td>
              <td>{{Tier_3_Magic_Resist}}</td>
            </tr>
            <tr>
              <td>Armor</td>
              <td>{{Tier_1_Armor}}</td>
              <td>{{Tier_2_Armor}}</td>
              <td>{{Tier_3_Armor}}</td>
            </tr>
            <tr>
              <td>Health Regen</td>
              <td>{{Tier_1_Health_Regen}}</td>
              <td>{{Tier_2_Health_Regen}}</td>
              <td>{{Tier_3_Health_Regen}}</td>
            </tr>
          </tbody>
        </template>
      </v-simple-table>
    </v-card-text>
  </v-card>
</template>



<script>
export default {
  props: {
    Name: {
      type: String,
      required: true
    },
    Alliances: [String],
    Tier: {
      type: String,
      required: true
    },
    Tier_1_Health: {
      type: String,
      required: true
    },
    Tier_2_Health: {
      type: String,
      required: true
    },
    Tier_3_Health: {
      type: String,
      required: true
    },
    Mana: {
      type: String
    },
    Tier_1_DPS: {
      type: String,
      required: true
    },
    Tier_2_DPS: {
      type: String,
      required: true
    },
    Tier_3_DPS: {
      type: String,
      required: true
    },
    Tier_1_AD_MIN: {
      type: String,
      required: true
    },
    Tier_1_AD_Max: {
      type: String,
      required: true
    },
    Tier_2_AD_MIN: {
      type: String,
      required: true
    },
    Tier_2_AD_Max: {
      type: String,
      required: true
    },
    Tier_3_AD_MIN: {
      type: String,
      required: true
    },
    Tier_3_AD_Max: {
      type: String,
      required: true
    },
    Tier_1_Attack_Rate: {
      type: String,
      required: true
    },
    Tier_2_Attack_Rate: {
      type: String,
      required: true
    },
    Tier_3_Attack_Rate: {
      type: String,
      required: true
    },
    Move_Speed: {
      type: String,
      required: true
    },
    Attack_Range: {
      type: String,
      required: true
    },
    Tier_1_Magic_Resist: {
      type: String,
      required: true
    },
    Tier_2_Magic_Resist: {
      type: String,
      required: true
    },
    Tier_3_Magic_Resist: {
      type: String,
      required: true
    },
    Tier_1_Armor: {
      type: String,
      required: true
    },
    Tier_2_Armor: {
      type: String,
      required: true
    },
    Tier_2_Armor: {
      type: String,
      required: true
    },
    Tier_1_Health_Regen: {
      type: String,
      required: true
    },
    Tier_2_Health_Regen: {
      type: String,
      required: true
    },
    Tier_3_Health_Regen: {
      type: String,
      required: true
    },
    Hero_Image: {
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
    },
    Lore_Text: {
      type: String,
      required: true
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