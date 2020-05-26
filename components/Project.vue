<template>
  <a v-bind:href="item.href" target="_blank" v-bind:class="{ 'cat-grey': !hasCategory }">
    <img v-bind:src="item.img" alt="" />
    <div class="gallery-hover">
      <div class="hover-inner">
        <span class="type">{{ item.type }}</span>
        <span class="name">{{ item.name }}</span>
        <span class="client">Client: {{ item.client }}</span>
      </div>
    </div>
  </a>
</template>
<script>
export default {
  props: ['item', 'category'],
  computed: {
    hasCategory () {
      // `this` points to the vm instance
      return this.category === 'all' || this.item.tags.includes(this.category)
    }
  }
}
</script>
<style>
.cat-grey img {
  filter: grayscale(100%);
  opacity: 0.25;
}

@keyframes appear {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>
