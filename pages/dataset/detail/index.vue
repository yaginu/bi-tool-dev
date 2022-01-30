<template>
	<v-tabs>
		<v-tab href="#tab-1">Preview</v-tab>
		<v-tab href="#tab-2">Summary</v-tab>
		<v-tab href="#tab-3">Visualization</v-tab>
		<v-tab-item value="tab-1">
			<DataPreview />
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
}
</script>