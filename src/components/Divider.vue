<template>
  <div class="divider">
    <img src="~@/assets/images/divider.png" />
  </div>
</template>

<script>
export default {
  name: "Divider",
};
</script>

<style lang="scss" scoped>
.divider {
  padding-left: $padding-vertical;
  padding-right: $padding-vertical;
  padding-bottom: 10px;
  img {
    width: 100%;
  }
}
</style>
