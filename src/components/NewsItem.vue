<template>
    <li class="news__item">
        <div class="upvote">
            <div class="upvote__triangle"></div>
            <span class="upvote__count">{{story.score}}</span>
        </div>
        <div class="news__body">
            <a :href="story.url" target="_blank" class="news__title">
                {{story.title}}
            </a>
            <div class="news__details">
                By <a :href="`https://news.ycombinator.com/user?id=${story.by.id}`" target="_blank" class="news__link">{{story.by.id}}</a> 3 hours ago | 
                <a :href="`https://news.ycombinator.com/item?id=${story.id}`" target="_blank" class="news__link">{{story.descendants}} comments</a>
            </div>
        </div>
    </li>
</template>

<script>
export default {
    props:{
        story: Object
    }
}
</script>

<style>

</style>