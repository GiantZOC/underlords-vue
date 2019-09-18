<template>
  <v-layout>
    <v-row>
      <v-col v-for="Alliance in Alliances" :key="Alliance.name" class="col-sm-4 col-12">
        <AllianceCard v-bind="Alliance"></AllianceCard>
      </v-col>
      <!-- <v-col class="col-sm-4 col-12"><BloodBoundCard></BloodBoundCard></v-col>
      <v-col class="col-sm-4 col-12"><BrawnyCard></BrawnyCard></v-col>
      <v-col class="col-sm-4 col-12"><AssassinCard></AssassinCard></v-col>
      <v-col class="col-sm-4 col-12"><AssassinCard></AssassinCard></v-col>
      <v-col class="col-sm-4 col-12"><AssassinCard></AssassinCard></v-col>-->
    </v-row>
  </v-layout>
</template>

<script>
import AllianceCard from '~/components/Alliances/AllianceCard.vue'
//import BloodBoundCard from '~/components/Alliances/Bloodbound.vue'
//import BrawnyCard from '~/components/Alliances/Brawny.vue'

export default {
  name: 'Alliances',
  components: {
    AllianceCard
  },
  data() {
    return {
      Alliances: [
        {
          name: 'assassin',
          title: 'Assassin',
          color: 'rgb(153, 50, 204)',
          unit_names: [
            'bounty_hunter',
            'bloodseeker',
            'morphling',
            'queenofpain',
            'phantom_assassin',
            'slark',
            'viper',
            'sand_king',
            'templar_assassin'
          ],
          alliance_bonus: [
            {
              unit_count: 3,
              description:
                'All Assassins gain a 15% chance to Critical Hit for 300% Damage'
            },
            {
              unit_count: 6,
              description:
                'All Assassins gain a 25% chance to Critical Hit for 400% Damage'
            }
          ],
          alliance_max_bonus_count: 6,
          height: '28%'
        },
        {
          name: 'bloodbound',
          title: 'Blood-Bound',
          color: 'rgb(153, 50, 204)',
          unit_names: ['ogre_magi', 'warlock'],
          alliance_bonus: [
            {
              unit_count: 2,
              description:
                'When a Blood-Bound unit dies, all other Blood-Bound units deal +125% Attack Damage for the rest of the battle'
            }
          ],
          alliance_max_bonus_count: 2,
          height: '45%'
        },
        {
          name: 'brawny',
          title: 'Brawny',
          color: 'rgb(153, 50, 204)',
          unit_names: ['axe', 'beastmaster', 'juggernaut', 'disruptor'],
          alliance_bonus: [
            {
              unit_count: 2,
              description:
                'All Brawny units gain +30 maximum HP for each kill they have.'
            },
            {
              unit_count: 4,
              description:
                'All Brawny units gain +60 maximum HP for each kill they have.'
            }
          ],
          alliance_max_bonus_count: 4,
          height: '45%'
        },
        {
          name: 'deadeye',
          title: 'Deadeye',
          color: 'rgb(153, 50, 204)',
          unit_names: ['bloodhunter', 'gyrocopter', 'sniper'],
          alliance_bonus: [
            {
              unit_count: 2,
              description:
                'All Deadeye units focus their attacks on the lowest-health enemy.'
            },
          ],
          alliance_max_bonus_count: 2,
          height: '45%'
        },
        {
          name: 'demon',
          title: 'Demon',
          color: 'rgb(153, 50, 204)',
          unit_names: ['chaos_knight', 'queenofpain', 'shadow_fiend', 'terrorblade', 'doom'],
          alliance_bonus: [
            {
              unit_count: 1,
              description:
                'All Demon units gain +50% Pure Damage. Active when you have only one type of Demon unit on the board'
            },
          ],
          alliance_max_bonus_count: 1,
          height: '90%'
        },
        {
          name: 'hunter',
          title: 'Demon Hunter',
          color: 'rgb(153, 50, 204)',
          unit_names: ['chaos_knight', 'queenofpain', 'shadow_fiend', 'terrorblade', 'doom'],
          alliance_bonus: [
            {
              unit_count: 1,
              description:
                'All Demon units gain +50% Pure Damage. Active when you have only one type of Demon unit on the board'
            },
          ],
          alliance_max_bonus_count: 1,
          height: '90%'
        }
      ]
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
</style>

