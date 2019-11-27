<template>
    <header class="header">
        <div class="header__logo">
            <img src="@/assets/YC.png" alt="YC logo">
        </div>
        <nav class="nav">
            <div class="nav__user hide-sm">
                <img src="@/assets/hn-hacker.png" alt="Users' Image">
                <span>Ire</span>
            </div>
            
            <input type="checkbox" name="nav_checkbox" class="nav__checkbox hidden" id="nav__checkbox">

            <label for="nav__checkbox" class="nav__checkbox show-sm">
                <div class="nav__toggle--bg">
                    <div class="nav__toggle"></div>
                </div>
            </label>

            <div class="nav__background show-sm"></div>

            <div class="mobile__nav show-sm">
                <div class="nav__user">
                    <img src="@/assets/hn-hacker.png" alt="User's Image">
                    <span>Ire</span>
                </div>
                <app-nav></app-nav>
            </div>
        </nav>
    </header> 
</template>

<script>
import appNav from './Nav';
export default {
    components: {
        appNav
    }
}
</script>