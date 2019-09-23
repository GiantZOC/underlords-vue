<template>
  <div v-if="Hero">
    <v-card>
      <v-card-title>{{Hero.Name}}</v-card-title>
      
      <v-img
        max-width="400"
        :src="require(`~/static${Hero.Hero_Image}`)"
        :srcset="require(`~/static${Hero.Hero_Image}`).srcSet"
        :lazy-src="require(`~/static${Hero.Hero_Image}`).placeholder"
      ></v-img>
<v-card-text>
      <v-row>
        <v-col>Level</v-col>
        <v-col>Star 1</v-col>
        <v-col>Star 2</v-col>
        <v-col>Star 3</v-col>
      </v-row>
      <v-row>
        <v-col>Health</v-col>
        <v-col>{{Hero.Tier_1_Health}}</v-col>
        <v-col>{{Hero.Tier_2_Health}}</v-col>
        <v-col>{{Hero.Tier_3_Health}}</v-col>
      </v-row>
      <v-row>
        <v-col>Mana</v-col>
        <v-col>{{Hero.Mana}}</v-col>
        <v-col>{{Hero.Mana}}</v-col>
        <v-col>{{Hero.Mana}}</v-col>
      </v-row>
      <v-row>
        <v-col>DPS</v-col>
        <v-col>{{Hero.Tier_1_DPS}}</v-col>
        <v-col>{{Hero.Tier_2_DPS}}</v-col>
        <v-col>{{Hero.Tier_3_DPS}}</v-col>
      </v-row>
      <v-row>
        <v-col>Attack Damage</v-col>
        <v-col>{{Hero.Tier_1_AD_MIN}}/{{Hero.Tier_1_AD_Max}}</v-col>
        <v-col>{{Hero.Tier_2_AD_MIN}}/{{Hero.Tier_2_AD_Max}}</v-col>
        <v-col>{{Hero.Tier_3_AD_MIN}}/{{Hero.Tier_3_AD_Max}}</v-col>
      </v-row>
      <v-row>
        <v-col>Attack Rate</v-col>
        <v-col>{{Hero.Tier_1_Attack_Rate}}</v-col>
        <v-col>{{Hero.Tier_2_Attack_Rate}}</v-col>
        <v-col>{{Hero.Tier_3_Attack_Rate}}</v-col>
      </v-row>
      <v-row>
        <v-col>Move Speed</v-col>
        <v-col>{{Hero.Move_Speed}}</v-col>
        <v-col>{{Hero.Move_Speed}}</v-col>
        <v-col>{{Hero.Move_Speed}}</v-col>
      </v-row>
      <v-row>
        <v-col>Magic Resist</v-col>
        <v-col>{{Hero.Tier_1_Magic_Resist}}</v-col>
        <v-col>{{Hero.Tier_2_Magic_Resist}}</v-col>
        <v-col>{{Hero.Tier_3_Magic_Resist}}</v-col>
      </v-row>
      <v-row>
        <v-col>Armor</v-col>
        <v-col>{{Hero.Tier_1_Armor}}</v-col>
        <v-col>{{Hero.Tier_2_Armor}}</v-col>
        <v-col>{{Hero.Tier_3_Armor}}</v-col>
      </v-row>
      <v-row>
        <v-col>Health Regen</v-col>
        <v-col>{{Hero.Tier_1_Health_Regen}}</v-col>
        <v-col>{{Hero.Tier_2_Health_Regen}}</v-col>
        <v-col>{{Hero.Tier_3_Health_Regen}}</v-col>
      </v-row>
      <div v-if="Hero.Lore_Text">
        <v-card-text>{{Hero.Lore_Text}}</v-card-text>
      </div>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
import getHero from '~/apollo/queries/getHero'

export default {
  apollo: {
    Hero: {
      query: getHero,
      prefetch: ({ route }) => ({ heroId: route.params.id }),
      variables() {
        return { heroId: this.$route.params.id }
      }
    }
  },
  head() {
    return {
      title: this.Hero ? `${this.Hero.Name}` : 'Loading'
    }
  }
}
</script>