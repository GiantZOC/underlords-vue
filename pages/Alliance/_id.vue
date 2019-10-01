<template>
    <AllianceCard v-if="Alliance" v-bind="Alliance"></AllianceCard>
</template>

<script>
import getAllianceByName from '~/apollo/queries/getAllianceByName'
import AllianceCard from '~/components/AllianceCard'

export default {
  name: 'Alliance',
  components: {
    AllianceCard
  },
  apollo: {
    Alliance: {
      query: getAllianceByName,
      prefetch: ({ route }) => ({ allianceName: route.params.id }),
      variables() {
        return { allianceName: this.$route.params.id }
      }
    }
  },
  head() {
    return {
      title: this.Alliance ? `${this.Alliance.title}` : 'Loading'
    }
  }
}

</script>