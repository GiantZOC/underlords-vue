<template>



  <v-card>
    <v-img class="hero_image"
      :src="require(`~/static${Hero_Image}`)"
      :srcset="require(`~/static${Hero_Image}`).srcSet"
      :lazy-src="require(`~/static${Hero_Image}`).placeholder"
    >
    <div class="title_blur">
    <v-card-title class="hero_title align-end fill-height" style="text-shadow: 0 1px 0 black;"><h3>{{Name}}</h3></v-card-title>
    </div>
    </v-img>
    

    <v-card-text></v-card-text>
  </v-card>
</template>

<style>
/* .hero_title::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: inherit;
  background-attachment: fixed;
  -webkit-filter: blur(12px);
  filter: blur(12px);
} */

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
  content: "";
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
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5)
}
.title_blur > .hero_title > h3 {
  margin: 0;
  color: white;
  position: relative;
  z-index: 1;
}

</style>

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