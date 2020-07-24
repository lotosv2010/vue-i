<template>
  <div id="app" class="container">
    <div class="swiper-container">
      <div class="swiper-wrapper">
        <div class="swiper-slide" v-for="item in steps" :key="item.title">
          <div class="status">
            <Button type="primary">{{item.title}}</Button>
          </div>
        </div>
      </div>
    </div>
    <div class="swiper-button-prev" @click="prev"></div>
    <div class="swiper-button-next" @click="next"></div>
  </div>
</template>
<script>
// import style
// import 'swiper/swiper.scss'
// If you use Swiper 6.0.0 or higher
import 'swiper/swiper-bundle.css'
import Swiper from 'swiper'
export default {
  data() {
    return {
      sp: null,
      steps: [
        { dateLabel: 'January 2017', title: 'Maintenance0' },
        { dateLabel: 'February 2017', title: 'Maintenance1' },
        { dateLabel: 'March 2017', title: 'Maintenance6' },
        { dateLabel: 'April 2017', title: 'Maintenance7' },
        { dateLabel: 'May 2017', title: 'Maintenance8' },
        { dateLabel: 'June 2017', title: 'Maintenance9' },
        { dateLabel: 'July 2017', title: 'Maintenanceh' },
        { dateLabel: 'July 2017', title: 'Maintenance2' },
        { dateLabel: 'July 2017', title: 'Maintenance3' },
        { dateLabel: 'July 2017', title: 'Maintenance4' },
        { dateLabel: 'July 2017', title: 'Maintenance5' }
      ]
    }
  },
  mounted() {
    this.sp = new Swiper('.swiper-container', {
      slidesPerView: 3,
      grabCursor: true,
      spaceBetween: 30,
      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      }
    })
  },
  methods: {
    prev() {
      this.sp.slidePrev()
      console.log('pre')
    },
    next() {
      this.sp.slideNext()
      console.log('next')
    }
  }
}
</script>
<style>
body {
  background: #e8eeff;
}
#app {
  padding: 50px 0;
}
.container{
  position: relative;
  width: 500px;
  margin: 0 auto;
}
.swiper-button-prev, .swiper-container-rtl .swiper-button-next {
  left: -20px;
}
.swiper-button-next, .swiper-container-rtl .swiper-button-prev {
  right: -20px;
}
</style>