<template>
    <h1 v-if="level === 1">{{ text }}</h1>
    <h2 v-if="level === 2">{{ text }}</h2>
    <h3 v-if="level === 3">{{ text }}</h3>
    <h4 v-if="level === 4">{{ text }}</h4>
    <h5 v-if="level === 5">{{ text }}</h5>
    <h6 v-if="level === 6">{{ text }}</h6>
</template>

<script>
export default {
    props: ['text', 'level'],
}
</script>