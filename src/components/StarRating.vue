<template>
    <div v-if="isFloat(stars)">
        <span class="material-icons my-auto fs-14  text-warning" v-for="star in checkInt(stars)">
            grade
        </span>
        <span class="material-icons my-auto fs-14  text-warning">
            star_half
        </span>
    </div>
    <div v-else>
        <span class="material-icons my-auto fs-14  text-warning" v-for="star in stars">
            grade
        </span>
    </div>
</template>

<script setup lang="ts">


interface Props {
    stars: number
}

const props = withDefaults(defineProps<Props>(), {

});


const isFloat = (val: number) => {
    if (typeof val === 'number' && !Number.isNaN(val) && !Number.isInteger(val)) {
        return true
    }
    return false
}

const checkInt = (val: number) => {
    return Math.floor(val)
}



</script>

<style scoped lang="scss">
</style>