<script setup lang="ts">
defineOptions({
	name: 'ModulesIndex'
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
        class="x-modules"
        :title="{ text: 'Modules', anchor: 12 }"
        :currentItem="currentItem"
        :nextPage="nextPage"
        :items="[
        { text: 'empathize', anchor: 14 }, // 0
        { text: 'extra params', anchor: 17 }, // 1
        { text: 'facets', anchor: 18 }, // 2
        { text: 'history queries', anchor: 21 }, // 3
        { text: 'next queries', anchor: 24 }, // 4
        { text: 'popular searches', anchor: 27 }, // 5
        { text: 'query suggestions', anchor: 29 }, // 6
        { text: 'related tags', anchor: 30 }, // 7
        { text: 'scroll', anchor: 32 }, // 8
        { text: 'search', anchor: 34 }, // 9
        { text: 'search box', anchor: 36 }, // 10
        { text: 'tagging', anchor: 38 }, // 11
        { text: 'url', anchor: 39 }, // 12
        { text: 'recommendations', anchor: 40 }, // 13
        { text: 'identifier results', anchor: 42 }, // 14
        { text: 'queries preview', anchor: 43 }, // 15
        { text: 'semantic queries', anchor: 45 }, // 16
        { text: 'experience controls', anchor: 46 } // 17
        ]"
    />
</template>
