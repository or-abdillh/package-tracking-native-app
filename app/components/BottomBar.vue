<style scoped>

.bottom-bar {
    border-top-width: 2px;
    border-top-color: #343434;
}

</style>

<template>
    <FlexboxLayout row="1" justifyContent="space-around" alignItems="center" class="bottom-bar" paddingTop="22">
        <Image v-for="menu in menus" :key="menu" :src="menu.icon" width="18" stretch="none" />
    </FlexboxLayout>
</template>

<script>

import Vue from 'vue';
import { FlexboxLayout, Image } from '@nativescript/core';

export default Vue.extend({
    data() {

        return {

            menus: [
                { name: "home", icon: "~/assets/icons/house.png" },
                { name: "map", icon: "~/assets/icons/location-dot.png" },
                { name: "search", icon: "~/assets/icons/search.png" },
                { name: "profile", icon: "~/assets/icons/circle-user.png" },
            ]
        }
    }
})

</script>
