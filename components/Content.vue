<template>
    <div v-for="item in content">
        <Text v-if="item.element === 'text'" :text="item.text" />
        <Heading v-if="item.element === 'heading'" :text="item.text" :level="item.level" />
        <List v-if="item.element === 'list'" :children="item.children" :type="item.type" />
    </div>
</template>

<script>
import Text from '@/components/contentcomponent/Text.vue';
import Heading from '@/components/contentcomponent/Heading.vue';
import List from '@/components/contentcomponent/List.vue';
export default {
    props: ['content'],
    components: {
        Text,
        Heading,
        List
    }
}
</script>

<style scoped>
.message {
	margin-bottom: 10px;
	padding: 10px;
	border-radius: 4px;
}
</style>
