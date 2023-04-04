<template>
    <div class="py-2">
        <div class="card" :class="`text-${colorText} ${backgroundColor}`">
            <div class="card-body">
                <h4 class="card-title">{{ title }}</h4>
                <p class="card-text">{{ text }}</p>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">

defineProps<{
    title: string;
    text: string;
    colorText: string;
    backgroundColor: string;
}>();

</script>

<style scoped></style>