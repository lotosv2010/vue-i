<template>
  <section id="app" class="container">
    <section class="context">
      <header>
        <div class="swiper-container">
          <div class="swiper-wrapper">
            <div class="swiper-slide" v-for="item in steps" :key="item.title">
              <div class="status">
                <Button type="primary" @click="setImg(item)">{{item.title}}</Button>
              </div>
            </div>
          </div>
        </div>
        <div class="swiper-button-prev" @click="prev"></div>
        <div class="swiper-button-next" @click="next"></div>
      </header>
      <article class="img">
        <img :src="img" alt="" srcset="">
      </article>
      <footer>
        <div>{{ label1 }}</div>
        <div>{{ label2 }}</div>
      </footer>
    </section>
  </section>
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
      img: 'https://file.iviewui.com/dist/7dcf5af41fac2e4728549fa7e73d61c5.svg',
      label1: '',
      label2: '',
      steps: [
        { dateLabel: 'January 2017', title: 'Maintenance0', scr: 'https://file.iviewui.com/dist/39ab5a22594134fba431ae055abc7744.jpg' },
        { dateLabel: 'February 2017', title: 'Maintenance1', scr: 'https://file.iviewui.com/dist/87c65fbc0f304cd48faa527a25d1b918.jpg' },
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
    setImg(data) {
      this.img = data.scr || 'https://file.iviewui.com/dist/87c65fbc0f304cd48faa527a25d1b918.jpg'
      this.label1 = data.dateLabel
      this.label2 = data.title
    },
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
  width: 600px;
  margin: 0 auto;
}
.context {
  padding: 10px;
}
header {
  position: relative;
}
.img {
  height: 400px;
  margin-top: 20px;
  border: 1px solid #000;
}
img {
  height: 100%;
  width: 100%;
  transition: all 1s;
}
.swiper-button-prev, .swiper-container-rtl .swiper-button-next {
  left: -20px;
}
.swiper-button-next, .swiper-container-rtl .swiper-button-prev {
  right: -20px;
}
</style>