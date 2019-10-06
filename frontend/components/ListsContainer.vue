<template>
  <v-card>
    <v-list-item v-for="list in this.$parent.lists" :key="list.id" two-line>
      <v-list-item-content>
        <h2>{{ list.title }}</h2>
      </v-list-item-content>
      <v-btn class="mx-2" fab dark color="pink" @click="removeList(list.id)">
        <v-icon>mdi-minus</v-icon>
      </v-btn>
      <v-btn class="mx-2" fab dark color="cyan" @click="$emit('set', list)">
        <v-icon>mdi-pencil</v-icon>
      </v-btn>
    </v-list-item>
  </v-card>
</template>

<script>
export default {
  methods: {
    removeList(id) {
      this.$axios
        .delete(`/api/v1/lists/${id}`)
        .then((res) => {
          const lists = this.$parent.lists.filter((l) => l.id !== id)
          this.$parent.lists = lists
        })
        .catch((err) => {
          console.log(err)
        })
    }
  }
}
</script>
