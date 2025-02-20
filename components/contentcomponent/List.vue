<template>
    <ul v-if="type === 'unordered'">
        <li v-for="child in children">
            <Text :text="child.text" />
        </li>
    </ul>
    <ol v-if="type === 'ordered'">
        <li v-for="child in children">
            <Text :text="child.text" />
        </li>
    </ol>
</template>

<script>
import Text from '@/components/contentcomponent/Text.vue';
export default {
    props: ['children', 'type'],
    components: {
        Text
    }
}
</script>