<template>
  <ItemTable></ItemTable>
</template>

<script>
import ItemTable from '~/components/ItemTable.vue'

export default {
  name: 'Items',
  components: {
    ItemTable
  },    
  head() {
    return {
      title: 'Items'
    }
  }
    
}
</script>
