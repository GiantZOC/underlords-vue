<template>
  <v-row>
    <v-col v-for="Hero in Heroes" :key="Hero.name" class="col-sm-3 col-12">
      <HeroCard v-bind="Hero"></HeroCard>
    </v-col>
  </v-row>
</template>

<script>
import HeroCard from '~/components/HeroCard.vue'
import getHeroes from '~/apollo/queries/getHeroes'

export default {
  name: 'Heroes',
  components: {
    HeroCard
  },
  data() {
    return {
      Heroes:[]
    }
  },
  apollo: {
    Heroes: {
      query: getHeroes
    }
  },
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
</style>

