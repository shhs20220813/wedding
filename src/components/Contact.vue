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
      <span class="account" @click='copyToClipBoard("83890204355037")'>국민 838902-04-355037</span><br />
      <span>어머니</span> &nbsp; <a href="tel:01095648880">이인향<img src="~@/assets/images/tel.png" class="tel" /></a><br />
      <span>신랑</span> &nbsp; <a href="tel:01072889018">천희수<img src="~@/assets/images/tel.png" class="tel" /></a><br />
    </p>

    <img src="~@/assets/images/cat.png" class="flower" />
    <h2 class="h2">
      신부측
    </h2>
    <p>
      <span>아버지</span> &nbsp; <a href="tel:01088146163">송재흥<img src="~@/assets/images/tel.png" class="tel" /></a><br />
      <span class="account" @click='copyToClipBoard("17365252068075")'>농협 173652-52-068075</span><br />
      <span>어머니</span> &nbsp; <a href="tel:01030295361">배은정<img src="~@/assets/images/tel.png" class="tel" /></a><br />
      <span>신부</span> &nbsp; <a href="tel:01042051128">송수현<img src="~@/assets/images/tel.png" class="tel" /></a><br />
    </p>
    
  </div>
</template>

<script>
export default {
  name: "Divider",
  methods: {
    copyToClipBoard(text) {
      this.$copyText(text);
      return this.$swal({
          toast: true,
          position: 'center-center',
          showConfirmButton: false,
          timer: 1500,
          icon: 'success',
          title: '계좌번호가 복사되었습니다.',
      })
    }
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
      font-size: 14px;
    }
    span.account {
      color: #295138;
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
      width: 15px;
    }
  } 
  a:hover { 
    text-decoration:none !important;
    color: #295138;
  }
}
</style>
