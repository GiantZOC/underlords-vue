<template>
  <LootTable></LootTable>
</template>

<script>
import LootTable from '~/components/LootTable.vue'

export default {
  name: 'Loot Rounds',
  components: {
    LootTable
  },    
  head() {
    return {
      title: 'Loot Rounds'
    }
  }
    
}
</script>
