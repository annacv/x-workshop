<script setup lang="ts">
defineOptions({
	name: 'ContentIndex'
})

const props = defineProps({
	currentItem: {
		type: Number,
		required: true,
		default: 0,
	},
	items: {
		type: Array,
		required: true,
		default: () => [],
	},
	title: {
		type: Object,
		required: false,
	},
	nextPage: {
		type: Number,
		required: false,
		default: 0,
	},
})

</script>

<template>
	<div class="flex flex-col justify-between h-full">
		<div class="flex flex-col">
			<Link :to=title.anchor><h5>{{ title.text }}</h5></Link>
			<div
				v-for="(item, index) in items"
				:key="index"
				class="text-xs capitalize x-item"
				:class="index === currentItem ? 'highlight': index < currentItem ? 'opacity-9 line-through' : 'opacity-9'"
				>
					<Link :to=item.anchor>· {{ item.text }}</Link>
			</div>
		</div>
		
		<Link
			:to="nextPage"
			class="rounded-full !border-solid border-[1px] !border-b-1 border-black px-[6px] !leading-[1.5] text-xs w-5 h-5 mt-8 mb-8"
		>></Link>
	</div>
</template>
