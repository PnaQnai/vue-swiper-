<template>
  <div>
    <div class="info-nav" v-if="!isSetTop">
      <swiper :options="infoNavOption" ref="infoSwiper">
        <!-- slides -->
        <swiper-slide v-for="(slide,index) in newsNav" :key="index">
          <p
            :class="['marquee-txt',currentIndex==index?'active':'']"
            @click="changeNav(index)"
          >{{slide}}</p>
        </swiper-slide>
      </swiper>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      newsNav: [
        "推荐",
        "郑州",
        "军事",
        "体育",
        "视频",
        "新视频",
        "推荐",
        "推荐"
      ],
      // 吸顶
      isSetTop: false,
      infoNavOption: {
        // loop: true,
        // spaceBetween: 10,
        freeMode: true,
        slidesPerView: "auto",
        watchSlidesProgress: true,
        watchSlidesVisibility: true
      },
      // 导航当前索引值
      currentIndex: 0
    };
  },
  methods: {
    // 切换导航
    changeNav: function(val) {
      console.log(val);

      // return;
      this.currentIndex = val;
      // this.formListData.typeCode = val.typeCode.join();
      // this.formListData.type = val.type;
      // this.formListData.isRecommend = val.isRecommend;
      // this.getList();
    }
  }
};
</script>
<style scoped>
.info-nav {
  position: initial;
  display: block;
  width: 100%;
  height: 106px;
  background: #fff;
  border-bottom: 10px solid #f8f8f8;
}
.info-nav.setTop {
  position: fixed;
  top: 88px;
  left: 0;
  z-index: 999;
  padding: 0 20px;
  border-bottom: 1px solid #d7d7d7;
}
.info-nav .swiper-container {
  height: 100%;
}
.info-nav .swiper-slide {
  width: auto;
  height: 100%;
}
.info-nav .marquee-txt {
  height: 100%;
  font-size: 30px;
  color: #9e9e9e;
  text-align: left;
  line-height: 130px;
  padding-right: 50px;
}
.info-nav .marquee-txt.active {
  font-size: 44px;
  color: #ff2d45;
  font-weight: bold;
}
</style>
