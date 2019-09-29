<template>
  <v-flex>
    <v-card>
      <v-card-text>
        <v-form>
          <v-text-field v-model="title" label="title" />
          <v-text-field v-model="excerpt" label="excerpt" type="text" />
        </v-form>
        <v-card-actions>
          <v-btn class="mx-2" fab dark color="indigo" @click="addList">
            <v-icon>mdi-plus</v-icon>
          </v-btn>
        </v-card-actions>
      </v-card-text>
    </v-card>
  </v-flex>
</template>

<script>
export default {
  data() {
    return {
      title: '',
      excerpt: ''
    }
  },
  methods: {
    addList() {
      this.$axios
        .$post('/api/v1/lists', { title: this.title, excerpt: this.excerpt })
        .then((res) => {
          this.$parent.lists.push(res)
        })
        .catch((err) => {
          console.log(err)
        })
    }
  }
}
</script>
