<template>
  <div>
    <LootTable class="mb-6"></LootTable>
    <RoundInfo></RoundInfo>
  </div>
</template>

<script>
import LootTable from '~/components/LootTable.vue'
import RoundInfo from '~/components/RoundInfo.vue'

export default {
  name: 'LootRounds',
  head() {
    return {
      title: 'Loot Rounds'
    }
  },
  components: {
    LootTable,
    RoundInfo
  },
}
</script>
