<template>
  <v-card>
      <v-list>
        <v-list-item>
          <v-list-item-avatar>
            <v-img
              :src="require('~/static/images/alliances/deadeye.png')"
              :srcset="require('~/static/images/alliances/deadeye.png').srcSet"
              :lazy-src="require('~/static/images/alliances/deadeye.png').placeholder"
            ></v-img>
          </v-list-item-avatar>

          <v-list-item-content>
            <h1>Deadeye</h1>
          </v-list-item-content>
        </v-list-item>
        <v-list-item>
          <div class="AllianceCard_UnitCountContainer">
            <div
              class="AllianceCard_Unit"
              style="background-color: rgb(166, 27, 27); height: 45%;"
            ></div>
            <div
              class="AllianceCard_Unit"
              style="background-color: rgb(166, 27, 27); height: 45%;"
            ></div>

            <div
              class="AllianceCard_Unit"
              style="background-color: initial; height: 45%;"
            ></div>
            <div
              class="AllianceCard_Unit"
              style="background-color: initial; height: 45%;"
            ></div>
          </div>
          All Brawny units gain +30 maximum HP for each kill they have.
        </v-list-item>
        <v-list-item>
          <div class="AllianceCard_UnitCountContainer">
            <div
              class="AllianceCard_Unit"
              style="background-color: rgb(166, 27, 27); height: 45%;"
            ></div>
            <div
              class="AllianceCard_Unit"
              style="background-color: rgb(166, 27, 27); height: 45%;"
            ></div>
            <div
              class="AllianceCard_Unit"
              style="background-color: rgb(166, 27, 27); height: 45%;"
            ></div>
            <div
              class="AllianceCard_Unit"
              style="background-color: rgb(166, 27, 27); height: 45%;"
            ></div>
          </div>
          
          All Brawny units gain +60 maximum HP for each kill they have
        </v-list-item>
      </v-list>
      <v-list>
        <v-list-item>
          <v-list-item-avatar height="80px" width="80px">
            <v-img
              :src="require('~/static/images/portraits/npc_dota_hero_axe_png.png')"
              :srcset="require('~/static/images/portraits/npc_dota_hero_axe_png.png').srcSet"
              :lazy-src="require('~/static/images/portraits/npc_dota_hero_axe_png.png').placeholder"
            ></v-img>
          </v-list-item-avatar>
          <v-list-item-avatar height="80px" width="80px">
            <v-img
              :src="require('~/static/images/portraits/npc_dota_hero_beastmaster_png.png')"
              :srcset="require('~/static/images/portraits/npc_dota_hero_beastmaster_png.png').srcSet"
              :lazy-src="require('~/static/images/portraits/npc_dota_hero_beastmaster_png.png').placeholder"
            ></v-img>
          </v-list-item-avatar>
          <v-list-item-avatar height="80px" width="80px">
            <v-img
              :src="require('~/static/images/portraits/npc_dota_hero_juggernaut_png.png')"
              :srcset="require('~/static/images/portraits/npc_dota_hero_juggernaut_png.png').srcSet"
              :lazy-src="require('~/static/images/portraits/npc_dota_hero_juggernaut_png.png').placeholder"
            ></v-img>
          </v-list-item-avatar>
        </v-list-item>
        <v-list-item>
          <v-list-item-avatar height="80px" width="80px">
            <v-img
              :src="require('~/static/images/portraits/npc_dota_hero_disruptor_png.png')"
              :srcset="require('~/static/images/portraits/npc_dota_hero_disruptor_png.png').srcSet"
              :lazy-src="require('~/static/images/portraits/npc_dota_hero_disruptor_png.png').placeholder"
            ></v-img>
          </v-list-item-avatar>
        </v-list-item>
      </v-list>
    </v-card>
</template>


