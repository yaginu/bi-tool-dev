<template>
	<v-row>
		<v-col cols="10">
			<v-data-table
				:headers="headers"
				:items="items"
			></v-data-table>
		</v-col>
	</v-row>
</template>

<script>
export default {
	name: 'DataPreview',
	props: {
		headers: Object,
		items: Object,
	},
}
</script>