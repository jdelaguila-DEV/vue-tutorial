<template>
    <!-- create apagination to navigate with the api -->
    <h1 class="py-3">Pagination</h1>
    <nav aria-label="Page navigation example">
        <ul class="pagination">
            <!-- <li @click="$emit('previus')" class="page-item"><a class="btn btn-outline-success">Previous</a></li> -->
            <!-- <li @click="$emit('next')" class="page-item"><a class="btn btn-outline-success">Next</a></li> -->
            <li @click="emit('previus')" class="page-item"><a class="btn btn-outline-success">Previous</a></li>
            <li @click="emit('next')" class="page-item"><a class="btn btn-outline-success">Next</a></li>
        </ul>
    </nav>
</template>

<script setup lang="ts">

// props

// defineProps<{
//     next: () => void;
//     previus: () => void;
// }>();

// emit

const emit = defineEmits(["next", "previus"]);

const nextPage = () => {
    console.log("me diste siguiente")
    emit('next');
}


</script>

<style scoped></style>