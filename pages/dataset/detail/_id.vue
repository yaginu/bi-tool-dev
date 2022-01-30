<template>
	<v-tabs>
		<v-tab href="#tab-1">Preview</v-tab>
		<v-tab href="#tab-2">Summary</v-tab>
		<v-tab href="#tab-3">Visualization</v-tab>
		<v-tab-item value="tab-1">
			<DataPreview :headers="headers" :items="items"/>
		</v-tab-item>
		<v-tab-item value="tab-2">
			<DataSummary />
		</v-tab-item>
		<v-tab-item value="tab-3">
			<DataVisualization />
		</v-tab-item>
	</v-tabs>
</template>

<script>
export default {
	name: 'DetasetDetail',
	async asyncData({ $axios, params }) {
		const url = `/api/dataset-detail/${params.id}`
		const response = await $axios.$get(url)
		const data = await JSON.parse(response.df)
		const headers = []
		for (const key of Object.keys(data[0])) {
			const column = {
				text: key,
				value: key,
			}
			headers.push(column)
		}
		const items = await Object.values(data)
		return { headers, items}
	},
}
</script>