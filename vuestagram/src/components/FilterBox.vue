<template>
  <div @click="fire" class="filter-item" :class="필터" :style="`background-image:url(${이미지})`">
    {{ 필터 }}
  </div>
</template>

<script>
export default {
  name: 'FilterBox',
	methods : {
		fire() {
			this.emitter.emit('박스클릭', this.필터);
		}
	},
  props: {
    이미지: String,
    필터: String,
  },
};
</script>

<style>
	.filter-item {
		text-align: center;
	}
</style>
