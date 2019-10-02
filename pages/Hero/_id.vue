<template>
  <v-card v-if="Hero" class="flex md12 sm12 lg8" dark>
    <div>
    <v-card-title>
      <h1 class="d-flex">{{Hero.name}}</h1>
      <div class="d-flex flex-nowrap ml-6">
        <div v-for="alliance in Hero.alliances" v-bind:key="alliance.name">
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
            :src="require(`~/static${Hero.hero_image}`)"
            :srcset="require(`~/static${Hero.hero_image}`).srcSet"
            :lazy-src="require(`~/static${Hero.hero_image}`).placeholder"
          ></v-img>
          <div v-if="Hero.ace_ability">
            <v-card-title>
              <v-avatar>
                <v-img
                  :src="require(`~/static/images/Ace_icon.png`)"
                  :srcset="require(`~/static/images/Ace_icon.png`).srcSet"
                  :lazy-src="require(`~/static/images/Ace_icon.png`).placeholder"
                ></v-img>
              </v-avatar>
              <div class="pl-2">{{Hero.ace_ability}}</div>
            </v-card-title>
            <v-card-text >{{Hero.ace_description}}</v-card-text>
          </div>
          <v-card
            class="no-shadow"
            v-for="ability in Hero.abilities"
            v-bind:key="ability.name"
            dark
          >
            <v-list-item three-line>
              <v-list-item-avatar size="125" tile>
                <v-img
                  class="hero_image"
                  :src="require(`~/static${ability.ability_image}`)"
                  :srcset="require(`~/static${ability.ability_image}`).srcSet"
                  :lazy-src="require(`~/static${ability.ability_image}`).placeholder"
                ></v-img>
              </v-list-item-avatar>

              <v-list-item-content class="align-self-start">
                <v-list-item-title v-text="ability.ability" class="text--primary"></v-list-item-title>
                <v-list-item-subtitle v-text="ability.description" class="text--primary"></v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
          </v-card>
          <div v-if="Hero.lore_text">
            <v-card-text class="font-italic">{{Hero.lore_text}}</v-card-text>
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
              <v-col>{{Hero.tier_1_health}}</v-col>
              <v-col>{{Hero.tier_2_health}}</v-col>
              <v-col>{{Hero.tier_3_health}}</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">
                Mana
              </v-col>
              <v-col>{{Hero.mana}}</v-col>
              <v-col>{{Hero.mana}}</v-col>
              <v-col>{{Hero.mana}}</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">DPS</v-col>
              <v-col>{{Hero.tier_1_dps}}</v-col>
              <v-col>{{Hero.tier_2_dps}}</v-col>
              <v-col>{{Hero.tier_3_dps}}</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">Attack Damage</v-col>
              <v-col>{{Hero.tier_1_ad_min}}-{{Hero.tier_1_ad_max}}</v-col>
              <v-col>{{Hero.tier_2_ad_min}}-{{Hero.tier_2_ad_max}}</v-col>
              <v-col>{{Hero.tier_3_ad_min}}-{{Hero.tier_3_ad_max}}</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">Attack Rate</v-col>
              <v-col>{{Hero.tier_1_attack_rate}}</v-col>
              <v-col>{{Hero.tier_2_attack_rate}}</v-col>
              <v-col>{{Hero.tier_3_attack_rate}}</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">Move Speed</v-col>
              <v-col>{{Hero.move_speed}}</v-col>
              <v-col>{{Hero.move_speed}}</v-col>
              <v-col>{{Hero.move_speed}}</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">Magic Resist</v-col>
              <v-col>{{Hero.tier_1_magic_resist}}</v-col>
              <v-col>{{Hero.tier_2_magic_resist}}</v-col>
              <v-col>{{Hero.tier_3_magic_resist}}</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">Armor</v-col>
              <v-col>{{Hero.tier_1_armor}}</v-col>
              <v-col>{{Hero.tier_2_armor}}</v-col>
              <v-col>{{Hero.tier_3_armor}}</v-col>
            </v-row>
            <v-row>
              <v-col class="subtitle-1 font-weight-bold">Health Regen</v-col>
              <v-col>{{Hero.tier_1_health_regen}}</v-col>
              <v-col>{{Hero.tier_2_health_regen}}</v-col>
              <v-col>{{Hero.tier_3_health_regen}}</v-col>
            </v-row>
          </v-card-text>
        </v-card>
      </div>
      <div v-if="Hero.ace_ability" class="flex md12 sm12 lg4">
        <v-card></v-card>
      </div>
      </div>
    </div>
  </v-card>
</template>

<script>
import getHeroByName from '~/apollo/queries/getHeroByName'

export default {
  apollo: {
    Hero: {
      query: getHeroByName,
      prefetch: ({ route }) => ({ heroName: route.params.id }),
      variables() {
        return { heroName: this.$route.params.id }
      }
    }
  },
  head() {
    return {
      title: this.Hero ? `${this.Hero.name}` : 'Loading'
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