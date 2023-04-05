<template>
    <!-- create apagination to navigate with the api -->
    <h1 class="py-3">Pagination</h1>
    <div aria-label="Page navigation">
        <ul class="pagination    ">
            <li class="page-item">
                <a class="page-link" @click="previus" aria-label="Previous">Previus</a>
            </li>
            <li class="page-item">
                <a class="page-link" @click="next" aria-label="Next">Next</a>
            </li>
        </ul>
    </div>
</template>

<script setup lang="ts">

defineProps<{
    next: () => void;
    previus: () => void;
}>();


</script>

<style scoped></style>