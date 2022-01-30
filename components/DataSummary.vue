<template>
	<v-row>
		<v-col cols="10">
			<v-data-table
				:headers="headers"
				:items="items"
				@click:row="handleClick"
			></v-data-table>
		</v-col>
	</v-row>
</template>

<script>
export default {
	name: 'DataPreview',
	data() {
		return {
			headers: [
				{
					text: 'ID',
					value: 'id',
				},
				{
					text: 'カラム1',
					value: 'column1',
				},
				{
					text: 'カラム2',
					value: 'column2',
				},
			],
			items: [
				{
					id: 1,
					column1: "aaaaaa",
					column2: "33",
				},
				{
					id: 2,
					column1: "aaaaaa",
					column2: "22"
				}
			]
		}
	},
	methods: {
		handleClick() {
			// alert("clicked")
		}
	}
}
</script>