<script>
import CreateAndEdit

export default {
  name: "category-item-create-and-edit",
  components: {CreateAndEdit},
  props: {
    item: null,
    visible: false,
  },
  emits: ['cancel-requested', 'save-requested'],
  data() {
    return {
      submitted: false,
    }
  },
  methods: {
    onCancelRequested() {
      this.$emit('cancel-requested');
    },
    onSaveRequested() {
      this.submitted = true;
      this.$emit('save-requested', this.item);
    },
  }
}
</script>

<template>
<create-and-edit :entity="item" :visible="visible" entity-name="Category"
                 @cancel-action-requested="onCancelRequested"
                  @save-action-requested="onSaveRequested">
  <template #content>
    
  </template>
</create-and-edit>
</template>

<style scoped>

</style>