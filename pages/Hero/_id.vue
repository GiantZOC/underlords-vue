<template>
  <v-card v-if="Hero" class="flex md12 sm12 lg8" dark>
    <div>
    <v-card-title>
      <h1 class="d-flex">{{Hero.Name}}</h1>
      <div class="d-flex flex-nowrap ml-6">
        <div v-for="alliance in Hero.Alliances" v-bind:key="alliance">
          <NuxtLink :to="`/Alliance/${alliance.name}`">
            <v-avatar>
              <v-img
                :src="require(`~/static/images/alliances/${alliance.name.toLowerCase()}.png`)"
                :srcset="require(`~/static/images/alliances/${alliance.name.toLowerCase()}.png`).srcSet"
                :lazy-src="require(`~/static/images/alliances/${alliance.name.toLowerCase()}.png`).placeholder"
              ></v-img>
            </v-avatar>
          </NuxtLink>
        </div>
      </div>
    </v-card-title>
    <div class="layout wrap">
      <div class="flex md12 sm12 lg6 my-border">
        <v-card class="no-shadow">
          <v-img
            :src="require(`~/static${Hero.Hero_Image}`)"
            :srcset="require(`~/static${Hero.Hero_Image}`).srcSet"
            :lazy-src="require(`~/static${Hero.Hero_Image}`).placeholder"
          ></v-img>
          <div v-if="Hero.Ace_Ability">
            <v-card-title>
              <v-avatar>
                <v-img
                  :src="require(`~/static/images/Ace_icon.png`)"
                  :srcset="require(`~/static/images/Ace_icon.png`).srcSet"
                  :lazy-src="require(`~/static/images/Ace_icon.png`).placeholder"
                ></v-img>
              </v-avatar>
              {{Hero.Ace_Ability}}
            </v-card-title>
            <v-card-text>{{Hero.Ace_Description}}</v-card-text>
          </div>
          <v-card
            class="no-shadow"
            v-for="Ability in Hero.Abilities"
            v-bind:key="Ability.Name"
            dark
          >
            <v-list-item three-line>
              <v-list-item-avatar size="125" tile>
                <v-img
                  class="hero_image"
                  :src="require(`~/static${Ability.Ability_Image}`)"
                  :srcset="require(`~/static${Ability.Ability_Image}`).srcSet"
                  :lazy-src="require(`~/static${Ability.Ability_Image}`).placeholder"
                ></v-img>
              </v-list-item-avatar>

              <v-list-item-content class="align-self-start">
                <v-list-item-title v-text="Ability.Ability" class="text--primary"></v-list-item-title>
                <v-list-item-subtitle v-text="Ability.Description" class="text--primary"></v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
          </v-card>
          <div v-if="Hero.Lore_Text">
            <v-card-text class="font-italic">{{Hero.Lore_Text}}</v-card-text>
          </div>
        </v-card>
      </div>
      <div class="flex md12 sm12 lg6">
        <v-card class="no-shadow">
          <v-card-title>Hero Stats</v-card-title>
          <v-card-text>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">Level</v-col>
              <v-col class="subtitle-1 font-weight-bold">Star 1</v-col>
              <v-col class="subtitle-1 font-weight-bold">Star 2</v-col>
              <v-col class="subtitle-1 font-weight-bold">Star 3</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">
                Health
              </v-col>
              <v-col>{{Hero.Tier_1_Health}}</v-col>
              <v-col>{{Hero.Tier_2_Health}}</v-col>
              <v-col>{{Hero.Tier_3_Health}}</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">
                Mana
              </v-col>
              <v-col>{{Hero.Mana}}</v-col>
              <v-col>{{Hero.Mana}}</v-col>
              <v-col>{{Hero.Mana}}</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">DPS</v-col>
              <v-col>{{Hero.Tier_1_DPS}}</v-col>
              <v-col>{{Hero.Tier_2_DPS}}</v-col>
              <v-col>{{Hero.Tier_3_DPS}}</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">Attack Damage</v-col>
              <v-col>{{Hero.Tier_1_AD_MIN}}-{{Hero.Tier_1_AD_Max}}</v-col>
              <v-col>{{Hero.Tier_2_AD_MIN}}-{{Hero.Tier_2_AD_Max}}</v-col>
              <v-col>{{Hero.Tier_3_AD_MIN}}-{{Hero.Tier_3_AD_Max}}</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">Attack Rate</v-col>
              <v-col>{{Hero.Tier_1_Attack_Rate}}</v-col>
              <v-col>{{Hero.Tier_2_Attack_Rate}}</v-col>
              <v-col>{{Hero.Tier_3_Attack_Rate}}</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">Move Speed</v-col>
              <v-col>{{Hero.Move_Speed}}</v-col>
              <v-col>{{Hero.Move_Speed}}</v-col>
              <v-col>{{Hero.Move_Speed}}</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">Magic Resist</v-col>
              <v-col>{{Hero.Tier_1_Magic_Resist}}</v-col>
              <v-col>{{Hero.Tier_2_Magic_Resist}}</v-col>
              <v-col>{{Hero.Tier_3_Magic_Resist}}</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">Armor</v-col>
              <v-col>{{Hero.Tier_1_Armor}}</v-col>
              <v-col>{{Hero.Tier_2_Armor}}</v-col>
              <v-col>{{Hero.Tier_3_Armor}}</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">Health Regen</v-col>
              <v-col>{{Hero.Tier_1_Health_Regen}}</v-col>
              <v-col>{{Hero.Tier_2_Health_Regen}}</v-col>
              <v-col>{{Hero.Tier_3_Health_Regen}}</v-col>
            </v-row>
          </v-card-text>
        </v-card>
      </div>
      <div v-if="Hero.Ace_Ability" class="flex md12 sm12 lg4">
        <v-card></v-card>
      </div>
      </div>
    </div>
  </v-card>
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

<style>
.column-label {
  font-weight: 700 !important;
}

.v-avatar {
  border-radius: 0px;
}

.my-border {
  border: 1px solid rgba(0, 0, 0, 0.12);
}

.no-shadow{
  box-shadow: 0px 0px 0px rgba(0, 0, 0, 0);
}
</style>