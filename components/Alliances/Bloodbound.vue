<template>
  <v-card>
      <v-list>
        <v-list-item>
          <v-list-item-avatar>
            <v-img
              :src="require('~/static/images/alliances/ogre.png')"
              :srcset="require('~/static/images/alliances/ogre.png').srcSet"
              :lazy-src="require('~/static/images/alliances/ogre.png').placeholder"
            ></v-img>
          </v-list-item-avatar>

          <v-list-item-content>
            <h1>Blood-Bound</h1>
          </v-list-item-content>
        </v-list-item>
        <v-list-item>
          <div class="AllianceCard_UnitCountContainer">
            <div
              class="AllianceCard_Unit"
              style="background-color: rgb(85, 107, 47); height: 45%;"
            ></div>
            <div
              class="AllianceCard_Unit"
              style="background-color: rgb(85, 107, 47); height: 45%;"
            ></div>
          </div>
          When a Blood-Bound unit dies, all other Blood-Bound units deal +125% Attack Damage for the rest of the battle
        </v-list-item>
      </v-list>
      <v-list>
        <v-list-item>
          <v-list-item-avatar height="80px" width="80px">
            <v-img
              :src="require('~/static/images/portraits/npc_dota_hero_ogre_magi_png.png')"
              :srcset="require('~/static/images/portraits/npc_dota_hero_ogre_magi_png.png').srcSet"
              :lazy-src="require('~/static/images/portraits/npc_dota_hero_ogre_magi_png.png').placeholder"
            ></v-img>
          </v-list-item-avatar>
          <v-list-item-avatar height="80px" width="80px">
            <v-img
              :src="require('~/static/images/portraits/npc_dota_hero_warlock_png.png')"
              :srcset="require('~/static/images/portraits/npc_dota_hero_warlock_png.png').srcSet"
              :lazy-src="require('~/static/images/portraits/npc_dota_hero_warlock_png.png').placeholder"
            ></v-img>
          </v-list-item-avatar>
        </v-list-item>
      </v-list>
    </v-card>
</template>


