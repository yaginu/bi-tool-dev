<template>
	<v-container>
		<v-row>
			<v-col cols="10">
				<v-data-table
					:headers="headers"
					:items="items"
					@click:row="handleClick"
				></v-data-table>
			</v-col>
		</v-row>
	</v-container>
</template>

<script>
export default {
	name: 'DatasetList',
	async asyncData({ $axios}) {
		const url = "/api/dataset-list/"
		const response = await $axios.$get(url)
		return {
			items: response
		}
	},
	data() {
		return {
			headers: [
				{
					text: 'Name',
					value: 'name',
				},
				// {
				// 	text: 'File',
				// 	value: 'file',
				// },
				{
					text: 'Comment',
					value: 'comment',
				},
				{
					text: 'Created at',
					value: 'created_at',
				},
				{
					text: 'Updated at',
					value: 'updated_at',
				},
			],
		}
	},
	methods: {
		handleClick(data) {
			this.$router.push(`/dataset/detail/${data.id}`)
		}
	}
}
</script>