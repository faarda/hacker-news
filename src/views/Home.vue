<template>
          <main class="home">
            <share-news></share-news>
            <section class="news card">
                <h4 class="card__header">
                    Top Stories
                </h4>

                <div class="card__body">
                    <p v-if="state == 'loading'" class="loading">Loading...</p>
                    <ul v-else class="news__list">
                      <news-item v-for="story in stories" :key="story.id" :story="story"></news-item>
                    </ul>
                </div>
            </section>
        </main>
</template>

<script>
import { HackerNews } from 'graphqlhub-schemas';
import { GraphQLSchema, graphql } from 'graphql';


import shareNews from '@/components/ShareNews';
import newsItem from '@/components/NewsItem';
export default {
  name: 'home',
  components:{
    shareNews,
    newsItem
  },
  data(){
    return {
      stories: [],
      state: "loading"
    }
  },
  mounted(){
    let schema = new GraphQLSchema({
      query: HackerNews.QueryObjectType
    });


    let query = `{
      topStories(limit: 30){
        id,
        by{
          id
        }
        time
        descendants
        title
        url
        score
      }
    }`;
    graphql(schema, query).then((result) => {
      this.stories = result.data.topStories;
      this.state = "done";
    });
  }
}
</script>


<style>
  .loading{
    text-align: center;
    padding: 25px;
    display: block;
  }
</style>
