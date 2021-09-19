<template>
  <div
	@click="fire"
    class="filter-item"
    :class="filter"
    :style="`background-image : url(${selectImage})`"
  ></div>
</template>

<script>
export default {
  name: 'FilterBox',
	methods: {
		fire() {
			
		}
	},
  props: {
    filter: String,
    selectImage: String,
  },
};
</script>

<style></style>
