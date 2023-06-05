<template>
     <div>
         <button class="button" @click="$emit('click')">
             {{ label }}
         </button>
     </div>
</template>

<script>
export default {
    name: 'AppButton',
    props: {
        label: {
            type: String
        }
    }
}

</script>

<style scoped>
.button {
    background: transparent;
    padding: 8px 22px;
    color: #FFFFFF;
    border: 1px solid #FFFFFF;
    font-weight: 500;
    font-size: 14px;
    line-height: 20px;
    cursor: pointer;
}
.button:hover {
    background: #FFFFFF;
    color: #000000;
}
</style>