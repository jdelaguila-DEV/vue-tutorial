<template>
    <div class="py-3">
        <div class="card" :class="`text-${colorText} bg-${backgroundColor}`">
            <div class="card-body">
                <h4 class="card-title">{{ id }} - {{ title }}</h4>
                <p class="card-text">{{ body }}</p>
                <button @click="emit('changeFavoriteName', title)" class="btn btn-outline-danger">
                    Favorite
                </button>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">

const emit = defineEmits(["changeFavoriteName"])

withDefaults(defineProps<{
    id: number;
    title: string;
    body: string;
    colorText?: string
    backgroundColor?: string
}>(), {
    colorText: 'dark',
    backgroundColor: 'light'
});

</script>

<style scoped></style>