<template>
  <div v-if="Item">
    <h3>{{ Item.name }}</h3>
  </div>
</template>

<script>
import getItem from '~/apollo/queries/getItem'
export default {
  apollo: {
    Item: {
      query: getItem,
      prefetch: ({ route }) => ({ itemId: route.params.id }),
      variables () {
        return { itemId: this.$route.params.id }
      }
    }
  },
  head () {
    return {
      title: (this.Item ? `${this.Item.name}` : 'Loading')
    }
  }
}
</script>