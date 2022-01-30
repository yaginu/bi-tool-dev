<template>
  <div>
    <v-form @submit.prevent="submitItem">
      <v-text-field
        v-model="item.name"
        label="Name"
        required
      ></v-text-field>
      <v-file-input
        v-model="item.file"
        truncate-length="15"
        accept=".csv"
      ></v-file-input>
      <v-text-field
        v-model="item.comment"
        label="Comment"
        required
      ></v-text-field>
      <v-btn
        color='primary'
        type='submit'
      >
        Upload
      </v-btn>
    </v-form>

  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      item: {
        name: '',
        file: '',
        comment: '',
      }
    }
  },
  methods: {
    async submitItem() {
      const  config = {
        headers: { 'content-type': 'multipart/form-data' }
      }
      const formData = new FormData()
      for (const data in this.item) {
        formData.append(data, this.item[data])
      }
      await this.$axios.$post('/api/dataset-create/', formData, config)
      this.$router.push('/dataset/list')
    }
  }
}
</script>
