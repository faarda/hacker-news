<template>
    <section class="share-news card">
        <h4 class="card__header">
            Submit News
        </h4>
        <div class="card__body">
            <form action="" class="share-news__form form">
                <div class="form__group">
                    <label for="" class="form__label">Title</label>
                    <input type="text" placeholder="Write title here" class="form__input">
                </div>
                <div class="form__group" v-show="!writeText">
                    <label for="" class="form__label">Url</label>
                    <input type="text" placeholder="News url here" class="form__input">
                </div>
                <div class="form__group" v-show="writeText">
                    <label for="" class="form__label">Text</label> 
                    <textarea placeholder="News text here" class="form__textarea"></textarea>
                </div>

                <div class="form__group form__footer">
                    <div class="post-toggle">
                        <span>Write text</span>
                        <label for="write-text">
                            <input class="form__switch--checkbox" v-model="writeText" id="write-text" type="checkbox" name="write-text">
                            <div class="form__switch">
                                <div class="toggle"></div>
                            </div>
                        </label>
                    </div>
                    <button type="submit" class="btn">Share</button>
                </div>
            </form>
        </div>
    </section>
</template>

<script>
export default {
    data(){
        return {
            writeText: false
        }
    }
}
</script>

<style>

</style>