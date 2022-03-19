<template>
  <div class="wellcome">
    <p class = "desc">
    </p>
    <img src="~@/assets/images/hands.png" class="hands" />
    <div class="description">
      our beloved summer
    </div>
    <div>
      <p>
        2016년 여름, 운명처럼 만나<br />
        천 눈에 반한 연인이 있었습니다.<br />
        희수는 넘치는 사랑을 가진 수현이 좋았고<br />
        수현은 생각이 깊은 희수가 좋았습니다.
      </p>
      <p>
        2022년 연인으로 맞는 일곱째 여름 <br />
        이제는 부부로서 서로를<br />
        영원히 사랑하기로 약속하려 합니다.<br />
        희수와 수현 그리고 양 가정이 하나되는<br />
        행복의 자리에 함께해 주세요.
      </p>
      <p class = "header">
        <br />
        2022년 8월 13일 토요일 오전 11시 30분<br />
        더채플앳논현 6층 라포레홀<br />
      </p>
    </div>
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
.wellcome {
  padding-top: 4px;
  padding-left: $padding-vertical;
  padding-right: $padding-vertical;
  text-align: center;

  .description {
    font-size: 12px;
    letter-spacing: 6px;
    margin-bottom: 30px;
    color: #295138;
  }

  .hands {
    width: 75px;
    margin-bottom: 16px;
  }
  p {
    margin-bottom: 16px;
    line-height: 24px;
    &.desc {
      color: #295238;
      font-size: 10px;
      opacity: 0.6;
      margin-bottom: 36px;
    }
    &.header {
      color: #295238;
    }
    &:last-child {
      margin-bottom: 40px;
    }
  }
}
</style>
