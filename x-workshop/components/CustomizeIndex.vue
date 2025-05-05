<script setup lang="ts">
defineOptions({
	name: 'CustomizeIndex'
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
        :title="{ text: 'Customizing', anchor: 53 }"
        :currentItem="currentItem"
        :nextPage="nextPage"
        :items="[
        { text: 'init options', anchor: 53 },
        { text: 'design system', anchor: 56 },
        { text: 'translations', anchor: 58 },
        { text: 'adapter', anchor: 60 },
        { text: 'modules', anchor: 62 },
        { text: 'event handling', anchor: 65 }
        ]"
    />
</template>
