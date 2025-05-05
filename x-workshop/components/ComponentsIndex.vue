<script setup lang="ts">
defineOptions({
	name: 'ComponentsIndex'
})

const props = defineProps({
	currentItem: {
		type: Number,
		required: true,
		default: 0,
	},
    nextPage: {
		type: Number,
		required: true,
		default: 0,
	}
})
</script>

<template>
    <ContentIndex
        :title="{ text: 'Components', anchor: 6 }"
        :currentItem="currentItem"
        :nextPage="nextPage"
        :items="[
        { text: 'animations', anchor: 7 },
        { text: 'base', anchor: 8 },
        { text: 'icons', anchor: 9 },
        { text: 'modals', anchor: 10 },
        { text: 'results', anchor: 11 }
        ]"
    />
</template>