<template>
  <div class="intro">
    <div class="image">
      <img src="~@/assets/images/intro-image.png" />
    </div>
    <audio src="~@/assets/media/bgm.mp3" autoplay loop />
  </div>
</template>

<script>
export default {
  name: "Intro",
  methods: {
    getOS() {
      var userAgent = window.navigator.userAgent,
        platform = window.navigator.platform,
        macosPlatforms = ["Macintosh", "MacIntel", "MacPPC", "Mac68K"],
        windowsPlatforms = ["Win32", "Win64", "Windows", "WinCE"],
        iosPlatforms = ["iPhone", "iPad", "iPod"],
        os = null;
      if (macosPlatforms.indexOf(platform) !== -1) {
        os = "Mac OS";
      } else if (iosPlatforms.indexOf(platform) !== -1) {
        os = "iOS";
      } else if (windowsPlatforms.indexOf(platform) !== -1) {
        os = "Windows";
      } else if (/Android/.test(userAgent)) {
        os = "Android";
      } else if (!os && /Linux/.test(platform)) {
        os = "Linux";
      }
      return os;
    },
  },
};
</script>

<style lang="scss" scoped>
.intro {
  // display: flex;
  // padding-top: 80px;
  // flex-direction: column;
  height: 100vh;
  line-height: 100vh;
  // min-height: 500px;
  // max-height: 780px;
  // background-color: #ffffff;
  // font-size: 0;
  .image {
    // display: flex;
    // flex: 1;
    // padding-left: $padding-vertical;
    // padding-right: $padding-vertical;
    // justify-content: center;
    
    // vertical-align: middle;
    // align-items: flex-start;
    // margin-top: 25vh;

    // position: absolute;
    // top: 50%;
    // margin-top: -188px;
    // vertical-align: middle;

    img {
      max-width: 100%;
      max-height: 100%;
      vertical-align: middle;
    }
  }
}
</style>