<template>
  <q-page class="">
    <div class="wrap">
      <div class="cards">
        <div class="cards__list q-pa-md">
          <h4 class="text-center">Список карточек</h4>
          <div class="row q-col-gutter-md">
            <div class="col-12 col-md-3 col-sm-6" v-for="(card, i) in cards" :key="i">
              <q-card class="card" v-ripple>
                <div class="q-pa-lg" style="padding: 20px;">
                  <q-img class="cursor-pointer" src="https://irtelecom.az/site/assets/files/1140/img51455_25477-1.jpg"></q-img>
                </div>
                <q-card-section>
                  <div class="desc">
                    {{card.desc.length > 100 ? card.desc.slice(0, 100) + '...' : card.desc}}
                  </div>
                </q-card-section>
                <q-card-section>
                  <div class="row card__sectionTop">
                    <div class="card__sectionTop-username">
                      <q-btn dense flat round icon="lens" size="6px" color="grey"/>
                      {{card.username}}
                    </div>
                    <q-space />
                    <div class="stars text-orange">
                      <q-icon name="mdi-star" color="orange"/><span>{{card.stars}}</span>
                      <span class="stars__quantity text-grey">({{card.quantity_stars}})</span>
                    </div>
                  </div>
                  <div class="row card__sectionBottom">
                    <q-btn
                      round dense flat
                      size="sm"
                      @click="card.liked = !card.liked">
                      <q-icon name="mdi-heart" :class="card.liked ? 'text-red' : ''"/>
                    </q-btn>
                    <q-space />
                    <div class="price">
                      от {{card.price}}<q-icon name="mdi-currency-rub"/>
                    </div>
                  </div>
                </q-card-section>
              </q-card>
            </div>
          </div>
        </div>
        <div class="cards__slider q-pa-md">
          <q-inner-loading :showing="visible" style="z-index: 9999;">
            <q-spinner-tail color="primary" size="3em" />
          </q-inner-loading>
          <h4 class="text-center">Слайдер карточек</h4>
          <carousel
            ref="carousel"
            :navigationEnabled="true"
            @page-change="navigationClick"
            :per-page="1"
            :perPageCustom="[[599, 2], [992, 3], [1170, 4]]"
          >
            <slide v-for="(slide, i) in slides" :key="i">
              <div class="q-pa-lg">
                <q-img
                  class="cursor-pointer"
                  contain :src="slide.img"
                  :ratio="1"
                  transition="fade"
                  spinner-color="info" />
              </div>
            </slide>
          </carousel>
        </div>
      </div>
    </div>
  </q-page>
</template>

<style>
</style>

<script>
import { Carousel, Slide } from 'vue-carousel'
export default {
  name: 'PageIndex',
  components: {
    Carousel,
    Slide
  },
  data () {
    return {
      visible: false,
      cards: [
        {
          id: 1,
          username: 'userName',
          img: 'https://irtelecom.az/site/assets/files/1140/img51455_25477-1.jpg',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi, dolorum hic libero minus nam obcaecati odit perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel.',
          view: 260,
          liked: false,
          stars: 5,
          quantity_stars: 260,
          price: 500
        },
        {
          id: 1,
          username: 'userName',
          img: 'https://irtelecom.az/site/assets/files/1140/img51455_25477-1.jpg',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi, dolorum hic libero minus nam obcaecati odit perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel.',
          view: 260,
          liked: false,
          stars: 5,
          quantity_stars: 260,
          price: 500
        },
        {
          id: 1,
          username: 'userName',
          img: 'https://irtelecom.az/site/assets/files/1140/img51455_25477-1.jpg',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi, dolorum hic libero minus nam obcaecati odit perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel.',
          view: 260,
          liked: false,
          stars: 5,
          quantity_stars: 260,
          price: 500
        },
        {
          id: 1,
          username: 'userName',
          img: 'https://irtelecom.az/site/assets/files/1140/img51455_25477-1.jpg',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi, dolorum hic libero minus nam obcaecati odit perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel.',
          view: 260,
          liked: false,
          stars: 5,
          quantity_stars: 260,
          price: 500
        },
        {
          id: 1,
          username: 'userName',
          img: 'https://irtelecom.az/site/assets/files/1140/img51455_25477-1.jpg',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi, dolorum hic libero minus nam obcaecati odit perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel.',
          view: 260,
          liked: false,
          stars: 5,
          quantity_stars: 260,
          price: 500
        },
        {
          id: 1,
          username: 'userName',
          img: 'https://irtelecom.az/site/assets/files/1140/img51455_25477-1.jpg',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi, dolorum hic libero minus nam obcaecati odit perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel.',
          view: 260,
          liked: false,
          stars: 5,
          quantity_stars: 260,
          price: 500
        },
        {
          id: 1,
          username: 'userName',
          img: 'https://irtelecom.az/site/assets/files/1140/img51455_25477-1.jpg',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi, dolorum hic libero minus nam obcaecati odit perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel.',
          view: 260,
          liked: false,
          stars: 5,
          quantity_stars: 260,
          price: 500
        },
        {
          id: 1,
          username: 'userName',
          img: 'https://irtelecom.az/site/assets/files/1140/img51455_25477-1.jpg',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi, dolorum hic libero minus nam obcaecati odit perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel.',
          view: 260,
          liked: false,
          stars: 5,
          quantity_stars: 260,
          price: 500
        },
        {
          id: 1,
          username: 'userName',
          img: 'https://irtelecom.az/site/assets/files/1140/img51455_25477-1.jpg',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi, dolorum hic libero minus nam obcaecati odit perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel.',
          view: 260,
          liked: false,
          stars: 5,
          quantity_stars: 260,
          price: 500
        },
        {
          id: 1,
          username: 'userName',
          img: 'https://irtelecom.az/site/assets/files/1140/img51455_25477-1.jpg',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi, dolorum hic libero minus nam obcaecati odit perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel.',
          view: 260,
          liked: false,
          stars: 5,
          quantity_stars: 260,
          price: 500
        },
        {
          id: 1,
          username: 'userName',
          img: 'https://irtelecom.az/site/assets/files/1140/img51455_25477-1.jpg',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi, dolorum hic libero minus nam obcaecati odit perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel perspiciatis sed sequi unde? Excepturi necessitatibus, perferendis! Deserunt distinctio esse fuga minus quaerat vel.',
          view: 260,
          liked: false,
          stars: 5,
          quantity_stars: 260,
          price: 500
        }
      ],
      slides: [
        { img: 'https://gstore.ua/images/1/apple-macbook-pro-15-retina-with-touchbar-256gb-2018-silver-65771088596572_small6.png' },
        { img: 'https://gstore.ua/images/1/apple-macbook-pro-15-retina-with-touchbar-256gb-2018-silver-65771088596572_small6.png' },
        { img: 'https://gstore.ua/images/1/apple-macbook-pro-15-retina-with-touchbar-256gb-2018-silver-65771088596572_small6.png' },
        { img: 'https://gstore.ua/images/1/apple-macbook-pro-15-retina-with-touchbar-256gb-2018-silver-65771088596572_small6.png' },
        { img: 'https://gstore.ua/images/1/apple-macbook-pro-15-retina-with-touchbar-256gb-2018-silver-65771088596572_small6.png' },
        { img: 'https://gstore.ua/images/1/apple-macbook-pro-15-retina-with-touchbar-256gb-2018-silver-65771088596572_small6.png' },
        { img: 'https://gstore.ua/images/1/apple-macbook-pro-15-retina-with-touchbar-256gb-2018-silver-65771088596572_small6.png' },
        { img: 'https://gstore.ua/images/1/apple-macbook-pro-15-retina-with-touchbar-256gb-2018-silver-65771088596572_small6.png' }
      ]
    }
  },
  mounted () {
  },
  methods: {
    navigationClick () {
      // this.$axios.get('url').then(res => {})
      if (this.$refs.carousel.getNextPage() === this.$refs.carousel.pageCount - 1) {
        this.visible = true
        setTimeout(() => {
          this.slides.push({ img: 'https://gstore.ua/images/1/apple-macbook-pro-15-retina-with-touchbar-256gb-2018-silver-65771088596572_small6.png' },
            { img: 'https://gstore.ua/images/1/apple-macbook-pro-15-retina-with-touchbar-256gb-2018-silver-65771088596572_small6.png' },
            { img: 'https://gstore.ua/images/1/apple-macbook-pro-15-retina-with-touchbar-256gb-2018-silver-65771088596572_small6.png' },
            { img: 'https://gstore.ua/images/1/apple-macbook-pro-15-retina-with-touchbar-256gb-2018-silver-65771088596572_small6.png' })
          setTimeout(() => {
            this.visible = false
          }, 400)
        }, 150)
      }
    }
  }
}
</script>
<style lang="stylus">
  .wrap
    width: 100%
    max-width: 1170px
    margin: auto
  .cards
    &__list
      .card
        .desc
          height: 60px
          overflow: hidden
          text-overflow:ellipsis
        &__sectionTop
          margin-bottom: 10px
          padding-bottom: 10px
          border-bottom: 1px solid #ccc
          color: #777
          .stars
            &__quantity
              display: inline-block
              margin-left: 5px
        &__sectionBottom
          .price
            color: green
            font-weight: bold
    &__slider
      .slider
        color: #000
    &__slider
      position: relative
  .VueCarousel-navigation
    button
      cursor: pointer
  .VueCarousel-navigation
    &-prev
      margin-left: 15px
    &-next
      margin-right: -15px
      transform translateY(-50%) !important
</style>
