<script setup lang='ts'>
import { onMounted, ref } from 'vue'
import { rmRecursive } from 'unstorage/drivers/utils/node-fs'

const selectedLang = ref()
const langs = ref([
  { name: 'RU', code: 'NY' },
  { name: 'EN', code: 'RM' }
])
const container = ref()
const element = ref()
const images = ref([
  {
    img: '/img/shield.svg'
  }, {
    img: '/img/$.svg'
  }, {
    img: '/img/soccer.svg'
  }, {
    img: '/img/m-green.svg'
  }, {
    img: '/img/shield.svg'
  }, {
    img: '/img/shield.svg'
  }, {
    img: '/img/soccer.svg'
  }
])
const imagesRef = ref([
  {
    img: '/img/shield.svg'
  }, {
    img: '/img/$.svg'
  }, {
    img: '/img/soccer.svg'
  }, {
    img: '/img/m-green.svg'
  }, {
    img: '/img/shield.svg'
  }, {
    img: '/img/shield.svg'
  }, {
    img: '/img/soccer.svg'
  }
])

onMounted(() => {

})
</script>

<template>
  <div class="h-full bg-[#110A1D] relative overflow-hidden">
    <div class="ellipse-1 absolute z-1 top-0 left-0" />
    <div class="index relative z-2 pt-3">
      <div class="container">
        <header class="header">
          <div class="h-5rem" />
          <ul class="menu-links--header flex justify-content-evenly">
            <li class="mx-3 font-light fadeindown animation-duration-1000">
              <a class="hover-underline hover-text-[#478BF9]" href="#">About us</a>
            </li>
            <li class="mx-3 font-light fadeindown animation-duration-1000 animation-delay-100">
              <a class="hover-underline hover-text-[#478BF9]" href="#">Brands</a>
            </li>
            <li class="mx-3 font-light fadeindown animation-duration-1000 animation-delay-200">
              <a class="hover-underline hover-text-[#478BF9]" href="#">Commissions</a>
            </li>
            <li class="mx-3 font-light fadeindown animation-duration-1000 animation-delay-300">
              <a class="hover-underline hover-text-[#478BF9]" href="#">News</a>
            </li>
            <li class="mx-3 font-light fadeindown animation-duration-1000 animation-delay-400">
              <a class="hover-underline hover-text-[#478BF9]" href="#">Contact us</a>
            </li>
            <li class="mx-3 font-light fadeindown animation-duration-1000 animation-delay-500">
              <a class="hover-underline hover-text-[#478BF9]" href="#">Careers</a>
            </li>
          </ul>

          <div class="flex align-items-center">
            <Dropdown v-model="selectedLang" class="lang-dropdown mr-3 fadeindown animation-duration-1000 animation-delay-600" :options="langs" option-label="name" placeholder="Select a Lang">
              <template #value="slotProps">
                <div v-if="slotProps.value" class="flex align-items-center mr-1">
                  <img class="mr-2" src="/img/globus.svg" alt="">
                  <h4 class="font-light">
                    {{ slotProps.value.name }}
                  </h4>
                </div>
              </template>
            </Dropdown>
            <Button class="login-button--login mr-3 fadeindown animation-duration-1000 animation-delay-700" severity="info" outlined>
              <span>LOG IN</span>
            </Button>
            <Button class="login-button--register mr-3 fadeindown animation-duration-1000 animation-delay-800">
              <span>SIGN UP</span>
            </Button>
          </div>
        </header>
      </div>
      <div class="container">
        <div class="banner ">
          <div class="grid  align-items-center relative overflow-hidden">
            <div class="col-12 sm:col-5">
              <h1 class="main-title">
                HOUSE OF <span class="text-[#478BF9]">GAMBLING</span>
              </h1>
              <p class="main-subtitle mt-2 mb-5">
                Raise your ROI with direct advertiser
              </p>
              <Button class="main-link mr-3 fadeindown animation-duration-1000 animation-delay-800">
                <span>Become a Partner</span>
              </Button>
            </div>
            <div class="col-12 sm:col-3">
              <img src="/img/radial.svg" class="absolute z-4 top-[70%] left-[30%]" alt="">
              <div class="px-2">
                <div class="grid ">
                  <div class="col-4 opacity-20">
                    <div ref="container" class="animation-box">
                      <div ref="element" class="flex flex-column animation-elem">
                        <img v-for="image in images" class="image w-full mb-3" :src="image.img" alt="">
                      </div>
                    </div>
                  </div>
                  <div class="col-4 opacity-60">
                    <div class="flex flex-column">
                      <img class="w-full mb-3" src="/img/m-pink.svg" alt="">
                      <img class="w-full mb-3" src="/img/timer.svg" alt="">
                      <img class="w-full mb-3" src="/img/crown.svg" alt="">
                      <img class="w-full mb-3" src="/img/globus.svg" alt="">
                      <img class="w-full mb-3" src="/img/m-pink.svg" alt="">
                      <img class="w-full mb-3" src="/img/timer.svg" alt="">
                      <img class="w-full mb-3" src="/img/crown.svg" alt="">
                      <img class="w-full mb-3" src="/img/globus.svg" alt="">
                    </div>
                  </div>
                  <div class="col-4 opacity-20">
                    <div class="flex flex-column">
                      <img class="w-full mb-3" src="/img/crown-2.svg" alt="">
                      <img class="w-full mb-3" src="/img/m-blue.svg" alt="">
                      <img class="w-full mb-3" src="/img/shield.svg" alt="">
                      <img class="w-full mb-3" src="/img/soccer.svg" alt="">
                      <img class="w-full mb-3" src="/img/shield.svg" alt="">
                      <img class="w-full mb-3" src="/img/crown.svg" alt="">
                      <img class="w-full mb-3" src="/img/m-blue.svg" alt="">
                      <img class="w-full mb-3" src="/img/shield.svg" alt="">
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="col-12 sm:col-4">
              <h2 class="blog-title text-center mb-3">
                BLOG
              </h2>
              <div class="bg-scroll ">
                <div class=" scroll-box">
                  <div class="flex flex-column gap-y-3">
                    <div class="blog-block blog-block--light">
                      <p class="blog-description mb-2">
                        Payment methods: Skrill, Neteller, webmoney, Bank transfer
                      </p>
                      <span>10.02.2023</span>
                    </div>
                    <div class="blog-block blog-block--dark">
                      <p class="blog-description mb-2">
                        Payment methods: Skrill, Neteller, webmoney, Bank transfer
                      </p>
                      <span>10.02.2023</span>
                    </div>
                    <div class="blog-block blog-block--dark">
                      <p class="blog-description mb-2">
                        Payment methods: Skrill, Neteller, webmoney, Bank transfer
                      </p>
                      <span>10.02.2023</span>
                    </div>
                    <div class="blog-block blog-block--dark">
                      <p class="blog-description mb-2">
                        Payment methods: Skrill, Neteller, webmoney, Bank transfer
                      </p>
                      <span>10.02.2023</span>
                    </div>
                    <div class="blog-block blog-block--dark">
                      <p class="blog-description mb-2">
                        Payment methods: Skrill, Neteller, webmoney, Bank transfer
                      </p>
                      <span>10.02.2023</span>
                    </div>
                    <div class="blog-block blog-block--dark">
                      <p class="blog-description mb-2">
                        Payment methods: Skrill, Neteller, webmoney, Bank transfer
                      </p>
                      <span>10.02.2023</span>
                    </div>
                    <div class="blog-block blog-block--dark">
                      <p class="blog-description mb-2">
                        Payment methods: Skrill, Neteller, webmoney, Bank transfer
                      </p>
                      <span>10.02.2023</span>
                    </div>
                    <div class="blog-block blog-block--dark">
                      <p class="blog-description mb-2">
                        Payment methods: Skrill, Neteller, webmoney, Bank transfer
                      </p>
                      <span>10.02.2023</span>
                    </div>
                    <div class="blog-block blog-block--dark">
                      <p class="blog-description mb-2">
                        Payment methods: Skrill, Neteller, webmoney, Bank transfer
                      </p>
                      <span>10.02.2023</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <footer class="footer">
        <div class="container">
          <div class="flex justify-content-between align-items-end pb-3 pt-6">
            <ul class="menu-links--footer flex">
              <li class="mx-3 font-light fadeindown animation-duration-1000">
                <a class="hover-underline hover-text-[#478BF9]" href="#">Terms & Conditions</a>
              </li>
              <li class="mx-3 font-light fadeindown animation-duration-1000 animation-delay-100">
                <a class="hover-underline hover-text-[#478BF9]" href="#">Cookies</a>
              </li>
              <li class="mx-3 font-light fadeindown animation-duration-1000 animation-delay-200">
                <a class="hover-underline hover-text-[#478BF9]" href="#">Contacts</a>
              </li>
              <li class="mx-3 font-light fadeindown animation-duration-1000 animation-delay-300">
                <a class="hover-underline hover-text-[#478BF9]" href="#">Careers</a>
              </li>
              <li class="mx-3 font-light fadeindown animation-duration-1000 animation-delay-400">
                <a class="hover-underline hover-text-[#478BF9]" href="#">Brand Guide</a>
              </li>
            </ul>
            <div class="flex flex-column align-items-end">
              <h3 class="icon-links__lable mb-3">
                Our social media:
              </h3>
              <div class="icon-links flex">
                <div class="relative icon-link">
                  <img class="dohover" src="/img/icon-bg.svg" alt="">
                  <img class="hovered" src="/img/icon-bg-hover.svg" alt="">
                  <img src="/img/Twitter.svg" class="absolute top-50 left-50 w-8" style="transform: translate(-50%,-50%)" alt="">
                </div>
                <div class="relative icon-link ml-2">
                  <img class="dohover" src="/img/icon-bg.svg" alt="">
                  <img class="hovered" src="/img/icon-bg-hover.svg" alt="">
                  <img src="/img/Facebook.svg" class="absolute top-50 left-50 w-8" style="transform: translate(-50%,-50%)" alt="">
                </div>
                <div class="relative icon-link ml-2">
                  <img class="dohover" src="/img/icon-bg.svg" alt="">
                  <img class="hovered" src="/img/icon-bg-hover.svg" alt="">
                  <img src="/img/Instagram.svg" class="absolute top-50 left-50 w-8" style="transform: translate(-50%,-50%)" alt="">
                </div>
                <div class="relative icon-link ml-2">
                  <img class="dohover" src="/img/icon-bg.svg" alt="">
                  <img class="hovered" src="/img/icon-bg-hover.svg" alt="">
                  <img src="/img/LinkedIn.svg" class="absolute top-50 left-50 w-8" style="transform: translate(-50%,-50%)" alt="">
                </div>
                <div class="relative icon-link ml-2">
                  <img class="dohover" src="/img/icon-bg.svg" alt="">
                  <img class="hovered" src="/img/icon-bg-hover.svg" alt="">
                  <img src="/img/YouTube.svg" class="absolute top-50 left-50 w-8" style="transform: translate(-50%,-50%)" alt="">
                </div>
                <div class="relative icon-link ml-2">
                  <img class="dohover" src="/img/icon-bg.svg" alt="">
                  <img class="hovered" src="/img/icon-bg-hover.svg" alt="">
                  <img src="/img/TikTok.svg" class="absolute top-50 left-50 w-8" style="transform: translate(-50%,-50%)" alt="">
                </div><div class="relative icon-link ml-2">
                  <img class="dohover" src="/img/icon-bg.svg" alt="">
                  <img class="hovered" src="/img/icon-bg-hover.svg" alt="">
                  <img src="/img/Telegram.svg" class="absolute top-50 left-50 w-8" style="transform: translate(-50%,-50%)" alt="">
                </div><div class="relative icon-link ml-2">
                  <img class="dohover" src="/img/icon-bg.svg" alt="">
                  <img class="hovered" src="/img/icon-bg-hover.svg" alt="">
                  <img src="/img/VK.svg" class="absolute top-50 left-50 w-8" style="transform: translate(-50%,-50%)" alt="">
                </div>
              </div>
            </div>
          </div>
        </div>
      </footer>
    </div>
  </div>
</template>

<style scoped></style>
