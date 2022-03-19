<template>
  <div class="funding">
    <img src="~@/assets/images/flower.png" class="flower" />
    <div class="description">
      contact
    </div>
    <h2 class="h2">
      신랑측
    </h2>
    <p>
      <span>아버지</span> &nbsp; <a href="tel:01021138109">천경민<img src="~@/assets/images/tel.png" class="tel" /></a><br />
      <span>어머니</span> &nbsp; <a href="tel:01095648880">이인향<img src="~@/assets/images/tel.png" class="tel" /></a><br />
      <span>신랑</span> &nbsp; <a href="tel:01072889018">천희수<img src="~@/assets/images/tel.png" class="tel" /></a><br />
    </p>

    <img src="~@/assets/images/cat.png" class="flower" />
    <h2 class="h2">
      신부측
    </h2>
    <p>
      <span>아버지</span> &nbsp; <a href="tel:01088146163">송재흥<img src="~@/assets/images/tel.png" class="tel" /></a><br />
      <span>어머니</span> &nbsp; <a href="tel:01030295361">배은정<img src="~@/assets/images/tel.png" class="tel" /></a><br />
      <span>신부</span> &nbsp; <a href="tel:01042051128">송수현<img src="~@/assets/images/tel.png" class="tel" /></a><br />
    </p>
    
  </div>
</template>

<script>
export default {
  name: "Divider",
  methods: {
  },
};
</script>

<style lang="scss" scoped>
.funding {
  padding-top: 48px;
  padding-left: $padding-vertical;
  padding-right: $padding-vertical;
  text-align: center;
  .description {
    font-size: 12px;
    letter-spacing: 6px;
    margin-bottom: 30px;
    color: #295138;
  }
  .flower {
    width: 70px;
    margin-bottom: 26px;
  }
  .h2 {
    font-size: 16px;
    font-weight: normal;
    margin-bottom: 24px;
    color: #295138;
  }
  p {
    margin-bottom: 32px;
    line-height: 24px;
    color: #202121;
    span {
      font-size: 13px;
    }
  }
  .link {
    display: inline-block;
    margin-top: 24px;
    color: #295238;
  }

  a { 
    text-decoration:none !important;
    color: #295138;
    .tel {
      vertical-align: middle;
      width: 14px;
    }
  } 
  a:hover { 
    text-decoration:none !important;
    color: #295138;
  }
}
</style>
