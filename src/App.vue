<template>
<div id="app">
    <app-header></app-header>
    <div class="page">
      <router-view />
      <aside class="card">
          <h4 class="card__header">
              Other links
          </h4>
          <nav class="side-nav">
              <app-nav></app-nav>
          </nav>
      </aside>
    </div>
</div>
</template>

<script>
import appHeader from '@/components/Header'
import appNav from '@/components/Nav'
export default {
    components: {
        appHeader,
        appNav
    }
}
</script>

<style>

</style>
