<template>
  <LootTable></LootTable>
</template>

<script>
import LootTable from '~/components/LootTable.vue'

export default {
  name: 'Loot Table',
  components: {
    LootTable
  },    
  head() {
    return {
      title: 'Loot Table'
    }
  }
    
}
</script>
