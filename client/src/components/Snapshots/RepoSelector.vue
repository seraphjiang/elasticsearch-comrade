<template>
  <v-combobox
    :items="repos"
    label="Select repository"
    item-text="id"
    @change="repo => $emit('select', repo.id)"
    class="mb-2"
  >
    <template v-slot:item="{ index, item }">
      <v-list-item-content>
        <v-chip dark label small>{{ item.id }} {{ item.location }} </v-chip>
      </v-list-item-content>
      <v-list-item-action>
        <v-chip dark label small color="success">{{ item.type.type }}</v-chip>
      </v-list-item-action>
    </template>
  </v-combobox>
</template>

<script>
export default {
  props: {
    repos: {
      type: Array,
      required: true
    }
  }
};
</script>

<style lang="scss" scoped></style>
