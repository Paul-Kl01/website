<template>
  <div class="member">
    <div id="java">
      <div class="name">
        {{ product.name }}
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "TeamMember",
    props: {
      product: {
        type: Object,
        default: () => {}
      }
    }
  };
</script>

<style lang="scss" scoped>
div.member {
  display: flex;
  flex-direction: row;
  padding-bottom: 10px;

  div.image {
    margin-right: 10px;
    width: 44px;
    height: 44px;

    img {
      border-radius: 50%;
      width: 100%;
      height: 100%;
    }
  }

  div.info {
    display: flex;
    flex-direction: column;
  }
}
</style>
