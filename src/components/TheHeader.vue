<template>
    <header class="header">
        <div class="global-container container">
            <p @click="$router.push('/')">TO<span>DO</span>S</p>
        <app-button
            v-if="pageIsHome"
            label="СОЗДАТЬ"
            @click="$router.push('/create')"
        />
        <app-button
            v-else
            label="НАЗАД"
            @click="$router.push('/')"
        />
        </div>
    </header>
</template>

<script>

import AppButton from "@/components/ui/AppButton.vue";
export default {
    name: 'TheHeader',
    components: {
        AppButton
    },
    computed: {
        pageIsHome() {
            return this.$route.name === 'home'
        }
    }
}




</script>

<style scoped>
.header {
    background: #2F2F2F;
}
.container {
    width: 85%;
    display: flex;
    padding: 12px;
    justify-content: space-between;
    align-items: center;
    margin: 0 auto;
}
.header p {
    color: #FFFFFF;
    font-weight: 700;
    font-size: 18px;
    line-height: 26px;
    cursor: pointer;
}
.header p span {
    color: #FC5151;
}

</style>
