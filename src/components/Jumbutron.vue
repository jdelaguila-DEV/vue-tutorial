<template>
    <!-- create a jumbutron with a photo behind with opacity-->
    <div class="p-4 p-md-5 mb-4 text-white rounded bg-dark">
        <div class="col-md-6 px-0">
            <h1 class="display-4 fst-italic">{{ title }}</h1>
            <p class="lead my-3">{{ text }}</p>
            <p class="lead mb-0"><a href="#" class="text-white fw-bold">Continue reading...</a></p>
            <button
                class="btn Swap the background-color utility and add a `.text-*` color utility to mix up the jumbotron look. Then, mix and match with additional component themes and more."
                type="button">Example button</button>
        </div>
    </div>
</template>

<script setup lang="ts">

defineProps<{
    title: string;
    text: string;
}>();

</script>

<style scoped></style>