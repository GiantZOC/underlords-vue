<template>
  <v-row>
    <v-col v-for="Alliance in Alliances" :key="Alliance.name" class="col-sm-3 col-12">
      <AllianceCard v-bind="Alliance"></AllianceCard>
    </v-col>
  </v-row>
</template>

<script>
import AllianceCard from '~/components/AllianceCard.vue'
import getAlliances from '~/apollo/queries/getAlliances'

export default {
  name: 'Alliances',
  components: {
    AllianceCard
  },
  data() {
    return {
      Alliances: []
    }
  },
  apollo: {
    Alliances: {
      query: getAlliances
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

