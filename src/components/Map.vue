<template>
  <div class="map">
    <div class="map-container" ref="gal">
      <div class="location">
        <img src="~@/assets/images/goose.png" class="goose" />
        <div class="description">
          location
        </div>
        <p class="black" @click='copyToClipBoard("서울특별시 강남구 논현로 549 더채플앳논현 6층 라포레홀")'>
          서울특별시 강남구 논현로 549<br />
          더채플앳논현 6층 라포레홀<br /><br />
        </p>
      </div>
      <vue-daum-map
          :appKey="appKey"
          :center.sync="center"
          :level.sync="level"
          :mapTypeId="mapTypeId"
          :libraries="libraries"
          @load="onLoad"
          style="height:240px;"/>
    </div>
    <div class="cover">
      <div class="navi-apps">
        <a v-bind:href="tmapUrl">
          <div class="ico_comm ico_tmap"><img src="~@/assets/images/icons/tmap.png"/></div>
          <div class="link">T맵</div>
        </a>
      </div>
      <div class="navi-apps">
        <a v-bind:href="kakaoTaxiUrl">
          <div class="ico_comm ico_taxi"><img src="~@/assets/images/icons/kakaot.png"/></div>
          <div class="link">카카오택시</div>
        </a>
      </div>
      <div class="navi-apps">
        <a v-bind:href="navermapUrl">
          <div class="ico_comm ico_navermap"><img src="~@/assets/images/icons/navermap.png"/></div>
          <div class="link">네이버맵</div>
        </a>
      </div>
      <div class="navi-apps">
        <a v-bind:href="kakaomapUrl">
          <div class="ico_comm ico_kakaomap"><img src="~@/assets/images/icons/kakaomap.png"/></div>
          <div class="link">카카오맵</div>
        </a>
      </div>
    </div>
  </div>
</template>

<script>

import VueDaumMap from 'vue-daum-map'

export default {
  name: "Map",
  components: {VueDaumMap},
  data() {
    return {
      scrollX: 0,
      width: 320,
      appKey: '0eb0011898072edefda09e3c737acbb8', // 테스트용 appkey
      center: {lat: 37.5050412, lng: 127.0343413}, // 지도의 중심 좌표
      level: 3, // 지도의 레벨(확대, 축소 정도),
      mapTypeId: VueDaumMap.MapTypeId.NORMAL, // 맵 타입
      libraries: ["drawing"], // 추가로 불러올 라이브러리
      map: null, // 지도 객체. 지도가 로드되면 할당됨.
      daum: null, // 다음 API 객체. 지도가 로드되면 할당됨.
      //////////////
      tmapUrl: "",
      kakaoTaxiUrl: "",
      navermapUrl: "",
      kakaomapUrl: ""

    };
  },
  mounted() {
    this.makeUrls()
  },
  methods: {
    // 지도가 로드 완료되면 load 이벤트 발생
    onLoad(map, daum) {
      this.map = map;
      this.daum = daum;

      // 지도를 클릭한 위치에 표출할 마커입니다
      var marker = new kakao.maps.Marker({
        // 지도 중심좌표에 마커를 생성합니다
        position: map.getCenter()
      });
      // 지도에 마커를 표시합니다
      marker.setMap(map);
    },
    makeUrls() {
      // 장소데이터의 이름정보 불러온 뒤
      const locationName = "더채플앳논현"
      this.tmapUrl = "tmap://search?name=" + locationName
      this.kakaoTaxiUrl = "https://t.kakao.com/launch?type=taxi&amp;dest_lat=37.5050412&amp;dest_lng=127.0343413&amp;ref=localweb"
      this.navermapUrl = "nmap://search?query=" + locationName + "&appname=shhs20220813.github.io/wedding"
      this.kakaomapUrl = "kakaomap://place?id=1992754829"
    },
    copyToClipBoard(text) {
      this.$copyText(text);
      return this.$swal({
          toast: true,
          position: 'center-center',
          showConfirmButton: false,
          timer: 1500,
          icon: 'success',
          title: '주소가 복사되었습니다.',
      })
    }
  }
};
</script>

<style lang="scss" scoped>

.map {
  margin-top: 18px;
  margin-bottom: 28px;
}

.navi-apps {
  align-content: center;
  position: relative;

  .ico_comm img {
    vertical-align: middle;
    width: 40px
  }

  div {
    text-align: center;
    padding-top: 10px;
  }

  a{
    text-decoration: none;
  }
}

.cover {
  display: flex;
  justify-content: space-between;
  margin: 22px 10% 22px 10%;
}

.link {
  color: #295238;
}

.location {
  // padding-bottom: 30px;
  padding-left: $padding-vertical;
  padding-right: $padding-vertical;
  text-align: center;
  color: #295138;
  .description {
    font-size: 12px;
    letter-spacing: 6px;
    margin-bottom: 30px;
    color: #295138;
  }
  
  .h2 {
    font-size: 16px;
    font-weight: normal;
    margin-bottom: 24px;
  }
  p {
    line-height: 24px;
    &.black {
      color: #202121;
    }
  }
  .goose {
    width: 90px;
    margin-top: 30px;
    margin-bottom: 20px;
  }
}

</style>
