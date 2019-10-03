<template>
  <div>
    <v-card v-for="round in lootRounds" v-bind:key="round.name" dark>
      <v-container style="padding: 0">
        <v-row>
          <v-col lg="3">
            <!-- <div class="flex md12 sm12 lg4 my-border"> -->
            <v-card-title style="padding: 8px" class="white darken-2 black--text font-weight-black">Round {{round.number}}: {{round.name}}</v-card-title>
            <div class="container">
              <div class="d-flex justify-center align-center">
                <v-img
                  class="justify-center align-center"
                  max-width="300px"
                  aspect-ratio="1"
                  :src="require(`~/static${round.image}`)"
                  :srcset="require(`~/static${round.image}`).srcSet"
                  :lazy-src="require(`~/static${round.image}`).placeholder"
                ></v-img>
              </div>
            </div>
            <!-- </div> -->
          </v-col>
          <v-col lg="9">
            <!-- <div class="mb-6"> -->
            <v-card-text>
              Strategy:
              {{round.strategy}}
            </v-card-text>
            <v-card-text>{{round.quote}}</v-card-text>
            <!-- </div> -->
          </v-col>
          <!-- </div> -->
        </v-row>
      </v-container>
    </v-card>
  </div>
</template>

<script>
export default {
  name: 'Loot Rounds',
  head() {
    return {
      title: 'Loot Rounds'
    }
  },
  data() {
    return {
      lootRounds: [
        {
          number: 1,
          name: 'Warmup',
          quote:
            '"Alright boys, I\'m not gonna lie: the chances of you surviving this are pretty low." ~ In which Grek motivates his talent',
          image: '/images/lootrounds/neutral_round1_vs_small_png.png',
          strategy: 'This round can be won with any hero.'
        },
        {
          number: 2,
          name: 'Sparring Match',
          quote:
            '"One hero? They got a chance. 2 heroes? No way in hell." ~ In which Grek acknowledges his fighter\'s limits',
          image: '/images/lootrounds/neutral_round2_vs_small_png.png',
          strategy: 'This round can be won with any two heroes.'
        },
        {
          number: 3,
          name: 'Gear Up',
          quote:
            '"Ya know what, just send the rest of \'em, maybe we can win the numbers game." ~ In which Grek makes a last ditch effort',
          image: '/images/lootrounds/neutral_round3_vs_png.png',
          strategy: 'This round can be won with any three heroes.'
        },
        {
          number: 10,
          name: 'First Intermission',
          quote:
            '"You think a sword can get through that armor? Magic, sure. But steel ain\'t doing much to these bad boys. ~ In which Grek likes what he sees',
          image: '/images/lootrounds/neutral_round10_vs_small_png.png',
          strategy:
            'This round can be won with strong alliance bonuses or upgraded units.  The creeps have high armor so magic damage or bleed is a big help.'
        },
        {
          number: 15,
          name: 'Dog and Pony Show',
          quote:
            "\"See that's what I'm talkin' about! They were so focused on the wolf in front they weren't ready for the wolves that came from behind. ~ In which Grek comments on a gladiator getting mauled",
          image: '/images/lootrounds/neutral_round15_vs_small_png.png',
          strategy:
            'The wolves behave like assassins and will attack your back line.  It can be helpful to group your units into a corner to help protect weaker spellcasters and ranged heroes.  These units have a chance to crit.  It is best to have high damage units and end the fight quickly.'
        },
        {
          number: 20,
          name: 'Bear Trap!',
          quote:
            "\"Naw naw... Tomato's the tough one, Potato's the smart one. But you watch: when one of these hellbears goes down, the other gets downright mean. ~ In which Grek talks hellbears",
          image: '/images/lootrounds/neutral_round20_vs_small_png.png',
          strategy:
            "The bears have a very strong bloodline buff.  It is best to split your team's dps between the two of them as much as possible.  This can be done by splitting them on the two halves of the battleground.  Any crowd control effects are also very useful for winning this fight."
        },
        {
          number: 25,
          name: 'Survival of the Fittest',
          quote:
            "\"These guys are harder to hit than they look. I can't tell you how many crews I've seen get eaten because they thought a couple axes would get the job done. ~ In which Grek has faith in his crew",
          image: '/images/lootrounds/neutral_round25_vs_small_png.png',
          strategy:
            'These creeps have high evasion (75%) and are hard to hit.  This greatly decreases the effectiveness of most heroes.  Even mages can have a hard time since most mana is gained from attacks.  A team with high sustainability can help win this fight.'
        },
        {
          number: 30,
          name: 'Big Dinos, Big Rewards',
          quote:
            "\"You know how fast Thunderhides heal? If you can't finish things quick, you better be ready for a long haul... anything in between and you're as good as dead. ~ In which Grek comments on the survivability of Thunderhides",
          image: '/images/lootrounds/neutral_round30_vs_small_png.png',
          strategy:
            'These creeps heal extremely quickly when they attack.  It is best to disable them with crowd control effects and then burst them down.  It is also possible to outlast the healing effects if enough of your team can survive the first few seconds of the fight.'
        },
        {
          number: 35,
          name: 'Things Are Heating Up',
          quote:
            '"I hope they clump together, the dragon eats em a lot faster when they clump together. ~ In which Grek is short on time',
          image: '/images/lootrounds/neutral_round35_vs_small_png.png',
          strategy:
            "This dragon deals damage to all heroes within 1 cell of it's target.  It is best to space out your units to minimize this damage.  The dragon also has 50% magic resist so mage teams can have a hard time."
        },
        {
          number: 40,
          name: "You're about to be trolled",
          quote:
            '"One way or another this thing is gonna be over quick. ~ In which Grek squeezes in a fight between meetings',
          image: '/images/lootrounds/neutral_round40_vs_small_png.png',
          strategy: 'If you made it this far you should steam roll this fight.'
        },
        {
          number: 45,
          name: "We've reached the endgame...",
          quote:
            "\"Armor won't save 'em. The year beast's claws can slice through anything. ~ In which Grek is overconfident 	",
          image: '/images/lootrounds/neutral_round45_vs_small_png.png',
          strategy:
            'It is rare to get this far with the current game balance.  This beast has cleave, 100% pure damage and 80% magic resist.'
        },
        {
          number: 50,
          name: "Correction, NOW we've reached the endgame..",
          quote:
            '"If you think Shadow Shaman can bring his chicken shenanigans to this fight I got bad news for ya. Magic doesn\'t do a damn thing to Roshan. ~ In which Grek bets on a sure thing 	',
          image: '/images/lootrounds/neutral_round50_vs_small_png.png',
          strategy:
            'Roshan is magic immune and has cleaving attacks.  Best of luck, I have never made it this far.'
        }
      ]
    }
  }
}
</script>
