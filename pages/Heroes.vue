<template>
  <div>
    <v-row>
      <v-col v-for="Hero in infiniteScrollHeroes.Heroes" :key="Hero.name" class="col-sm-3 col-12">
        <HeroCard v-bind="Hero"></HeroCard>
      </v-col>
    </v-row>
    <v-row>
      <v-col>
        <v-flex xs12 v-if="showMoreEnabled" column>
          <v-layout justify-center row>
            <v-btn color="info" @click="showMorePosts">Fetch More</v-btn>
          </v-layout>
        </v-flex>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import HeroCard from '~/components/HeroCard.vue'
//import getHeroes from '~/apollo/queries/getHeroes'
import getInfiniteScrollHeroes from '~/apollo/queries/getInfiniteScrollHeroes'
const pageSize = 8;

export default {
  name: 'Heroes',
  components: {
    HeroCard
  },
  data() {
    return {
      pageNum: 1,
      //showMore,
      //Heroes: []
    }
  },
  apollo: {
    infiniteScrollHeroes: {
      query: getInfiniteScrollHeroes,
      variables: {
        pageNum: 1,
        pageSize
      }
    }
  },
  computed: {
    showMoreEnabled() {
      return this.infiniteScrollHeroes && this.infiniteScrollHeroes.hasMore
    }
  },
  methods: {
    showMorePosts() {
      this.pageNum += 1
      //fetches more data and transform original result
      this.$apollo.queries.infiniteScrollHeroes.fetchMore({
        variables: {
          pageNum: this.pageNum,
          pageSize
        },
        updateQuery: (prevResult, { fetchMoreResult }) => {
          //console.log('previous result', prevResult.infiniteScrollPosts.posts);
          //console.log('fetch more result', fetchMoreResult);

          const newHeroes = fetchMoreResult.infiniteScrollHeroes.Heroes
          const hasMore = fetchMoreResult.infiniteScrollHeroes.hasMore
          //this.showMoreEnabled = hasMore;

          return {
            infiniteScrollHeroes: {
              __typename: prevResult.infiniteScrollHeroes.__typename,
              // merge previous posts with new posts
              Heroes: [...prevResult.infiniteScrollHeroes.Heroes, ...newHeroes],
              hasMore
            }
          }
        }
      })
    }
  },
  head() {
    return {
      title: 'Heroes'
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
  margin: 5px;
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

