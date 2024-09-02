<template>
  <div id="home">
    <q-layout
      view="hHh Lpr lff"
      container
      class="fixed-top"
      :style="{ height: drawer ? '100vh' : '90px', zIndex: 2 }"
    >
      <q-header class="text-white my-header">
        <q-toolbar class="row justify-between">
          <q-space v-if="$q.screen.gt.xs" />
          <q-tabs
            v-model="tab"
            v-if="$q.screen.gt.xs"
            active-color="primary"
            indicator-color="dark"
            class="text-black"
          >
            <q-tab name="home" label="Home" @click="moveTo('home')" />
            <q-tab name="about" label="About Me" @click="moveTo('about')" />
            <q-tab
              name="projects"
              label="Projects"
              @click="moveTo('projects')"
            />
          </q-tabs>
          <q-btn
            flat
            @click="drawer = !drawer"
            round
            dense
            icon="menu"
            color="black"
            v-if="$q.screen.xs"
          />
          <q-space />
        </q-toolbar>
      </q-header>
      <q-drawer
        v-model="drawer"
        :width="200"
        :height="500"
        class="absolute-top-left"
      >
        <q-scroll-area class="fit">
          <q-list padding class="menu-list">
            <q-item clickable v-ripple @click="moveTo('home')">
              <q-item-section avatar>
                <q-icon name="home" />
              </q-item-section>

              <q-item-section> Home </q-item-section>
            </q-item>

            <q-item active clickable v-ripple @click="moveTo('about')">
              <q-item-section avatar>
                <q-icon name="star" />
              </q-item-section>

              <q-item-section> About Me </q-item-section>
            </q-item>

            <q-item clickable v-ripple @click="moveTo('projects')">
              <q-item-section avatar>
                <q-icon name="drafts" />
              </q-item-section>

              <q-item-section> Projects </q-item-section>
            </q-item>
          </q-list>
        </q-scroll-area>
      </q-drawer>
    </q-layout>
  </div>

  <!-- <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
          Essential Links
        </q-item-label>

        <EssentialLink
          v-for="link in linksList"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer> -->

  <div class="container">
    <div class="gradient-background row justify-center items-center" id="home">
      <!-- <router-view /> -->
      <div class="column" style="padding-left: 7px; padding-right: 7px">
        <q-card bordered class="my-card q-px-lg">
          <div class="card-content">
            <q-card-section>
              <h2
                class="text-white text-weight-bold text-center"
                v-if="$q.screen.gt.xs"
              >
                Joshua Christian Limerson
              </h2>
              <h3
                class="text-white text-weight-bold text-center"
                v-if="$q.screen.xs"
              >
                Joshua Christian Limerson
              </h3>
              <div class="row justify-center">
                <p class="text-h5">
                  I am
                  <span class="typed" :data-typed-items="typedStrings"></span>
                </p>
              </div>
            </q-card-section>

            <q-separator inset />

            <q-card-section class="row justify-center q-pa-none">
              <div class="socialList">
                <a class="socialContainer containerOne" href="#">
                  <svg viewBox="0 0 16 16" class="socialSvg instagramSvg">
                    <path
                      d="M8 0C5.829 0 5.556.01 4.703.048 3.85.088 3.269.222 2.76.42a3.917 3.917 0 0 0-1.417.923A3.927 3.927 0 0 0 .42 2.76C.222 3.268.087 3.85.048 4.7.01 5.555 0 5.827 0 8.001c0 2.172.01 2.444.048 3.297.04.852.174 1.433.372 1.942.205.526.478.972.923 1.417.444.445.89.719 1.416.923.51.198 1.09.333 1.942.372C5.555 15.99 5.827 16 8 16s2.444-.01 3.298-.048c.851-.04 1.434-.174 1.943-.372a3.916 3.916 0 0 0 1.416-.923c.445-.445.718-.891.923-1.417.197-.509.332-1.09.372-1.942C15.99 10.445 16 10.173 16 8s-.01-2.445-.048-3.299c-.04-.851-.175-1.433-.372-1.941a3.926 3.926 0 0 0-.923-1.417A3.911 3.911 0 0 0 13.24.42c-.51-.198-1.092-.333-1.943-.372C10.443.01 10.172 0 7.998 0h.003zm-.717 1.442h.718c2.136 0 2.389.007 3.232.046.78.035 1.204.166 1.486.275.373.145.64.319.92.599.28.28.453.546.598.92.11.281.24.705.275 1.485.039.843.047 1.096.047 3.231s-.008 2.389-.047 3.232c-.035.78-.166 1.203-.275 1.485a2.47 2.47 0 0 1-.599.919c-.28.28-.546.453-.92.598-.28.11-.704.24-1.485.276-.843.038-1.096.047-3.232.047s-2.39-.009-3.233-.047c-.78-.036-1.203-.166-1.485-.276a2.478 2.478 0 0 1-.92-.598 2.48 2.48 0 0 1-.6-.92c-.109-.281-.24-.705-.275-1.485-.038-.843-.046-1.096-.046-3.233 0-2.136.008-2.388.046-3.231.036-.78.166-1.204.276-1.486.145-.373.319-.64.599-.92.28-.28.546-.453.92-.598.282-.11.705-.24 1.485-.276.738-.034 1.024-.044 2.515-.045v.002zm4.988 1.328a.96.96 0 1 0 0 1.92.96.96 0 0 0 0-1.92zm-4.27 1.122a4.109 4.109 0 1 0 0 8.217 4.109 4.109 0 0 0 0-8.217zm0 1.441a2.667 2.667 0 1 1 0 5.334 2.667 2.667 0 0 1 0-5.334z"
                    ></path>
                  </svg>
                </a>

                <a class="socialContainer containerTwo" href="#">
                  <svg viewBox="0 0 16 16" class="socialSvg twitterSvg">
                    <path
                      d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27s1.36.09 2 .27c1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8"
                    ></path>
                  </svg>
                </a>

                <a class="socialContainer containerThree" href="#">
                  <svg viewBox="0 0 448 512" class="socialSvg linkdinSvg">
                    <path
                      d="M100.28 448H7.4V148.9h92.88zM53.79 108.1C24.09 108.1 0 83.5 0 53.8a53.79 53.79 0 0 1 107.58 0c0 29.7-24.1 54.3-53.79 54.3zM447.9 448h-92.68V302.4c0-34.7-.7-79.2-48.29-79.2-48.29 0-55.69 37.7-55.69 76.7V448h-92.78V148.9h89.08v40.8h1.3c12.4-23.5 42.69-48.3 87.88-48.3 94 0 111.28 61.9 111.28 142.3V448z"
                    ></path>
                  </svg>
                </a>

                <a class="socialContainer containerFour" href="#">
                  <svg viewBox="0 0 16 16" class="socialSvg emailSvg">
                    <path
                      d="M2 2a2 2 0 0 0-2 2v8.01A2 2 0 0 0 2 14h5.5a.5.5 0 0 0 0-1H2a1 1 0 0 1-.966-.741l5.64-3.471L8 9.583l7-4.2V8.5a.5.5 0 0 0 1 0V4a2 2 0 0 0-2-2zm3.708 6.208L1 11.105V5.383zM1 4.217V4a1 1 0 0 1 1-1h12a1 1 0 0 1 1 1v.217l-7 4.2z"
                    ></path>
                    <path
                      d="M14.247 14.269c1.01 0 1.587-.857 1.587-2.025v-.21C15.834 10.43 14.64 9 12.52 9h-.035C10.42 9 9 10.36 9 12.432v.214C9 14.82 10.438 16 12.358 16h.044c.594 0 1.018-.074 1.237-.175v-.73c-.245.11-.673.18-1.18.18h-.044c-1.334 0-2.571-.788-2.571-2.655v-.157c0-1.657 1.058-2.724 2.64-2.724h.04c1.535 0 2.484 1.05 2.484 2.326v.118c0 .975-.324 1.39-.639 1.39-.232 0-.41-.148-.41-.42v-2.19h-.906v.569h-.03c-.084-.298-.368-.63-.954-.63-.778 0-1.259.555-1.259 1.4v.528c0 .892.49 1.434 1.26 1.434.471 0 .896-.227 1.014-.643h.043c.118.42.617.648 1.12.648m-2.453-1.588v-.227c0-.546.227-.791.573-.791.297 0 .572.192.572.708v.367c0 .573-.253.744-.564.744-.354 0-.581-.215-.581-.8Z"
                    ></path>
                  </svg>
                </a>
              </div>
            </q-card-section>
            <q-card-section class="row justify-center"
              ><q-btn color="primary" push class="bounceBtn">
                <div class="row items-center">
                  <q-icon left name="keyboard_arrow_down" />
                  <div class="text-center" @click="moveTo('about')">
                    Learn More
                  </div>
                </div>
              </q-btn></q-card-section
            >
          </div>
        </q-card>
      </div>
    </div>
    <div style="background-color: #ffffff" id="about">
      <div class="background-size row">
        <transition
          appear
          enter-active-class="animated fadeInLeftBig slower"
          leave-active-class="animated fadeInRightBig slower"
        >
          <div
            class="col-12 col-md-4 column container-about-image justify-center"
            style="max-width: 100%; z-index: 2"
          >
            <q-img
              src="../assets/polaroid.png"
              style="
                width: 400px;
                max-width: 100%;
                object-fit: contain;
                object-position: center;
                align-items: center;
              "
            />
          </div>
        </transition>
        <transition
          appear
          enter-active-class="animated fadeInRightBig slower"
          leave-active-class="animated fadeOut"
        >
          <div
            class="col-12 col-md-8 column container-about-desc"
            style="max-width: 100%; z-index: 2"
          >
            <div style="max-width: 100%">
              <p class="text-primary text-weight-medium">
                I am Joshua Christian Limerson,
              </p>
              <p class="text-blue-grey text-subtitle1 q-pr-xl text-justify">
                I am a graduate Computer Science (Global Class) student on BINUS
                UNIVERSITY. My passion on Computer Science subject itself lies
                on UI/UX Designer, Front-End Development, and animations. I
                always wanted to learn more about how can I improve my passion
                and ideas and to see new opportunities to expand my skills in
                every aspect.
              </p>
            </div>
            <div style="height: 200px" v-if="$q.screen.gt.xs"></div>
            <div class="row">
              <div class="col-12 col-md-6">
                <ul class="q-pl-none">
                  <li class="q-pb-sm">
                    <q-icon name="chevron_right" size="sm" color="primary" />
                    <strong class="text-h6 q-pr-md">Birth Date:</strong>
                    <span class="text-h6 text-weight-light"
                      >Singapore, 25 April 2001</span
                    >
                  </li>
                  <li class="q-pb-sm">
                    <q-icon name="chevron_right" size="sm" color="primary" />
                    <strong class="text-h6 q-pr-md">Phone:</strong>
                    <span class="text-h6 text-weight-light"
                      >+(62) 895 330 690 960</span
                    >
                  </li>
                  <li class="q-pb-sm">
                    <q-icon name="chevron_right" size="sm" color="primary" />
                    <strong class="text-h6 q-pr-md">City:</strong>
                    <span class="text-h6 text-weight-light"
                      >Batam, Indonesia</span
                    >
                  </li>
                </ul>
              </div>
              <div class="col-12 col-md-6">
                <ul class="q-pl-none">
                  <li class="q-pb-sm">
                    <q-icon name="chevron_right" size="sm" color="primary" />
                    <strong class="text-h6 q-pr-md">Age:</strong>
                    <span class="text-h6 text-weight-light">21</span>
                  </li>
                  <li class="q-pb-sm">
                    <q-icon name="chevron_right" size="sm" color="primary" />
                    <strong class="text-h6 q-pr-md">Email:</strong>
                    <span class="text-h6 text-weight-light"
                      >jcljoshualim@gmail.com</span
                    >
                  </li>
                  <li class="q-pb-sm">
                    <q-icon name="chevron_right" size="sm" color="primary" />
                    <strong class="text-h6 q-pr-md">Freelance:</strong>
                    <span class="text-h6 text-weight-light">Available</span>
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </transition>
        <div class="row container-about-divider">
          <q-space class="col-12 col-md-4" v-if="$q.screen.gt.xs" />
          <div class="col-12 col-md-8 q-px-md">
            <p class="text-white text-h5 text-weight-medium">Skills</p>
            <ChipList :chips="chips" />
          </div>
        </div>
      </div>
      <div class="bg-red" style="height: 100vh"></div>
    </div>
    <div
      style="background-color: #b2beb5"
      id="projects"
      class="background-size"
    >
      projects page
      <div class="row justify-center q-px-lg">
        <div
          v-for="(card, index) in cardsContent"
          :key="index"
          class="col-12 col-md-4 q-pa-md"
        >
          <q-card style="border-radius: 12px">
            <q-card-section class="q-pb-none">
              <div class="text-h6 q-pb-sm">{{ card.title }}</div>
              <div class="row">
                <div class="row col-6">
                  <q-icon name="schedule" size="xs" class="q-pr-sm" />
                  <div class="text-subtitle2">{{ card.date }}</div>
                </div>
                <div class="row col-6">
                  <q-icon name="person" size="xs" class="q-pr-sm" />
                  <div class="text-subtitle2">{{ card.role }}</div>
                </div>
              </div>
            </q-card-section>
            <img
              :src="card.image"
              class="q-pa-md"
              style="border-radius: 30px"
            />
            <q-card-section class="q-pt-none">
              {{ card.description }}
            </q-card-section>
          </q-card>
        </div>
      </div>
    </div>
  </div>
  <div v-if="!reachedBottom" class="scrolldown" style="--color: #0563bb">
    <div class="chevrons">
      <div class="chevrondown"></div>
      <div class="chevrondown"></div>
    </div>
  </div>
  <q-btn
    round
    v-if="reachedBottom"
    @click="scrollToTop"
    icon="navigation"
    color="primary"
    class="fixed-bottom-right q-mb-md q-mr-md bounceBtn"
  />
</template>

<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue';
import ChipList from 'src/components/chipList.vue';
import Typed from 'typed.js';

import figma from 'src/assets/Figma-logo.png';
import html from 'src/assets/HTML5-Badge.png';
import css from 'src/assets/CSS3-logo.png';
import javascript from 'src/assets/Javascript-logo.png';
import typescript from 'src/assets/Typescript-logo.png';
import vue3 from 'src/assets/Vue-logo.png';
import photoshop from 'src/assets/Photoshop.png';
import premierpro from 'src/assets/AdobePP-icon.png';
import aftereffect from 'src/assets/AdobeAE-icon.png';
import msoffice from 'src/assets/MSOffice-logo.png';
import canva from 'src/assets/Canva-icon.png';
import git from 'src/assets/Git-Icon.png';

const typedStrings =
  'a Designer, an Editor, a Web Developer, a Frontend Developer, a Graduate'; // This could be dynamic as well

const reachedBottom = ref<boolean>(false);

const handleScroll = () => {
  const documentHeight = document.documentElement.scrollHeight;
  const viewportHeight = window.innerHeight;
  const scrollTop = window.scrollY || window.pageYOffset;

  reachedBottom.value = scrollTop + viewportHeight >= documentHeight - 10;
};

const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' });
};

onMounted(() => {
  const typedElement = document.querySelector('.typed') as HTMLElement | null;

  if (typedElement) {
    const dataTypedItems = typedElement.getAttribute('data-typed-items');
    if (dataTypedItems) {
      const stringsArray = dataTypedItems.split(',');
      new Typed('.typed', {
        strings: stringsArray,
        loop: true,
        typeSpeed: 100,
        backSpeed: 50,
        backDelay: 2000,
      });
    }
  }

  const sections = [
    { id: 'home', element: document.getElementById('home') },
    { id: 'features', element: document.getElementById('about') },
    { id: 'contact-us', element: document.getElementById('projects') },
  ];

  const showContact = ref(false);
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          tab.value = entry.target.id;
          if (entry.target.id === 'contact-us') {
            showContact.value = true;
          } else {
            showContact.value = false;
          }
        }
      });
    },
    {
      root: null,
      threshold: 0.1,
    }
  );

  sections.forEach((section) => {
    if (section.element) {
      observer.observe(section.element);
    }
  });

  window.addEventListener('scroll', handleScroll);
  handleScroll(); // Initial check
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});

const tab = ref('home');

const drawer = ref(false);
const moveTo = (id: string) => {
  drawer.value = false;
  const targetElement = document.getElementById(id);
  if (targetElement) {
    setTimeout(() => {
      window.scrollTo({
        top: targetElement.offsetTop,
        behavior: 'smooth',
      });
    }, 25);
  }
};

// Define the chip data
const chips = [
  { color: '#e9e9e9', text: 'Figma', image: figma },
  { color: '#e9e9e9', text: 'HTML5', image: html },
  { color: '#e9e9e9', text: 'CSS', image: css },
  { color: '#e9e9e9', text: 'Javascript', image: javascript },
  { color: '#e9e9e9', text: 'Typescript', image: typescript },
  { color: '#e9e9e9', text: 'Vue3', image: vue3 },
  { color: '#e9e9e9', text: 'Photoshop', image: photoshop },
  { color: '#e9e9e9', text: 'Premier pro', image: premierpro },
  { color: '#e9e9e9', text: 'After Effect', image: aftereffect },
  { color: '#e9e9e9', text: 'Microsoft Office', image: msoffice },
  { color: '#e9e9e9', text: 'Canva', image: canva },
  { color: '#e9e9e9', text: 'Git', image: git },
];

interface projectsCard {
  title: string;
  date: string;
  role: string;
  image: string;
  description: string;
}

const cardsContent = ref<projectsCard[]>([
  {
    title: 'Our Changing Planet',
    date: 'September 2024',
    role: 'Designer',
    image: 'https://cdn.quasar.dev/img/mountains.jpg',
    description:
      'lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
  },
  {
    title: 'In this World',
    date: 'November 2024',
    role: 'Programmer',
    image: 'https://cdn.quasar.dev/img/parallax2.jpg',
    description:
      "The paper was blank. It shouldn't have been. There should have been writing on the paper, at least a paragraph if not more.",
  },
  {
    title: 'For Once and for All',
    date: 'December 2024',
    role: 'Engineer',
    image: 'https://picsum.photos/500/300',
    description:
      'Why do Americans have so many different types of towels? We have beach towels, hand towels, bath towels, dish towels, camping towels, quick-dry towels, and let’s not forget paper towels.',
  },
]);
</script>

<style scoped>
.container {
  overflow: hidden;
}

ul {
  list-style-type: none;
}
.background-size {
  width: 100vw; /* Full width */
  position: relative;
}

.container-about-divider {
  position: absolute; /* Absolute positioning */
  bottom: 35%; /* 20% from the bottom of the parent */
  left: 0; /* Align left */
  right: 0; /* Align right */
  background-image: linear-gradient(
    #1976d2,
    #42a5f0
  ); /* Example background color */
  padding: 10px; /* Add some padding */
}
.gradient-background {
  height: 100vh; /* Full height */
  width: 100vw; /* Full width */
  background: linear-gradient(45deg, #d42274, #3a7bd5, #d4d122);
  background-size: 600% 600%;
  animation: GradientBackground 30s ease infinite;
}

@keyframes GradientBackground {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

.my-header {
  /* From https://css.glass */
  background: rgba(255, 255, 255, 0.25);
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(5px);
  -webkit-backdrop-filter: blur(5px);
  border: 1px solid rgba(255, 255, 255, 0.25);
}

.my-card {
  /* From https://css.glass */
  background: rgba(255, 255, 255, 0.25);
  border-radius: 16px;
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(5px);
  -webkit-backdrop-filter: blur(5px);
  border: 1px solid rgba(255, 255, 255, 0.25);
  transition: box-shadow 0.3s ease; /* Transition for box-shadow */
}

.my-card:hover {
  box-shadow: 0 6px 40px rgba(0, 0, 0, 0.3); /* Enhanced shadow for zoom effect */
}

.socialList {
  width: fit-content;
  height: fit-content;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 25px 25px;
  gap: 20px;
  border-radius: 5em;
}

/* for all social containers*/
.socialContainer {
  width: 52px;
  height: 52px;
  border-radius: 50%;
  background-color: rgb(50, 50, 50);
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  transition-duration: 0.3s;
}
/* instagram*/
.containerOne:hover {
  background-color: #d62976;
  transition-duration: 0.3s;
}
/* twitter*/
.containerTwo:hover {
  background-color: #0d1117;
  transition-duration: 0.3s;
}
/* linkdin*/
.containerThree:hover {
  background-color: #0072b1;
  transition-duration: 0.3s;
}
/* Whatsapp*/
.containerFour:hover {
  background-color: #f90101;
  transition-duration: 0.3s;
}

.socialContainer:active {
  transform: scale(0.9);
  transition-duration: 0.3s;
}

.socialSvg {
  width: 17px;
}

.socialSvg path {
  fill: rgb(255, 255, 255);
}

.socialContainer:hover .socialSvg {
  animation: slide-in-top 0.3s both;
}

@keyframes slide-in-top {
  0% {
    transform: translateY(-50px);
    opacity: 0;
  }

  100% {
    transform: translateY(0);
    opacity: 1;
  }
}

.bounceBtn {
  animation: pulse 1s infinite;
  display: flex;
  justify-content: center;
  align-items: center;
  -moz-animation: bounce 2s infinite;
  -webkit-animation: bounce 2s infinite;
  animation: bounce 2s infinite;
}

@keyframes bounce {
  0%,
  20%,
  50%,
  80%,
  100% {
    -moz-transform: translateY(0);
    -ms-transform: translateY(0);
    -webkit-transform: translateY(0);
    transform: translateY(0);
  }
  40% {
    -moz-transform: translateY(-10px);
    -ms-transform: translateY(-10px);
    -webkit-transform: translateY(-10px);
    transform: translateY(-10px);
  }
  60% {
    -moz-transform: translateY(-5px);
    -ms-transform: translateY(-5px);
    -webkit-transform: translateY(-5px);
    transform: translateY(-5px);
  }
}

/* From Uiverse.io by mrhyddenn */
.scrolldown {
  --color: white;
  --sizeX: 30px;
  --sizeY: 50px;
  position: fixed; /* Change to fixed to stick to the viewport */
  bottom: 30px; /* Adjust distance from the bottom */
  right: 20px; /* Adjust distance from the right */
  width: var(--sizeX);
  height: var(--sizeY);
  border: calc(var(--sizeX) / 10) solid var(--color);
  border-radius: 50px;
  box-sizing: border-box;
  cursor: pointer;
}

.scrolldown::before {
  content: '';
  position: absolute;
  bottom: 30px;
  left: 50%;
  width: 6px;
  height: 6px;
  margin-left: -3px;
  background-color: var(--color);
  border-radius: 100%;
  animation: scrolldown-anim 2s infinite;
  box-sizing: border-box;
  box-shadow: 0px -5px 3px 1px #2a547066;
}

@keyframes scrolldown-anim {
  0% {
    opacity: 0;
    height: 6px;
  }

  40% {
    opacity: 1;
    height: 10px;
  }

  80% {
    transform: translate(0, 20px);
    height: 10px;
    opacity: 0;
  }

  100% {
    height: 3px;
    opacity: 0;
  }
}

.chevrons {
  padding: 6px 0 0 0;
  margin-left: -3px;
  margin-top: 48px;
  width: 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.chevrondown {
  margin-top: -6px;
  position: relative;
  border: solid var(--color);
  border-width: 0 3px 3px 0;
  display: inline-block;
  width: 10px;
  height: 10px;
  transform: rotate(45deg);
}

.chevrondown:nth-child(odd) {
  animation: pulse54012 500ms ease infinite alternate;
}

.chevrondown:nth-child(even) {
  animation: pulse54012 500ms ease infinite alternate 250ms;
}

@keyframes pulse54012 {
  from {
    opacity: 0;
  }

  to {
    opacity: 0.5;
  }
}

@media screen and (max-width: 600px) {
  #about {
    min-height: 100vh;
    .container-about-desc {
      justify-content: space-between;
      p:nth-child(1) {
        font-size: 30px;
      }
      p:nth-child(2) {
        text-align: center;
      }
    }
  }
}

@media screen and (max-width: 1024px) {
  #about {
    min-height: 100vh;
    .container-about-desc {
      justify-content: space-between;
      p:nth-child(1) {
        font-size: 36px;
      }
      p:nth-child(2) {
        text-align: center;
        font-size: 20px;
      }
    }
  }
}

@media screen and (min-width: 1024px) {
  #about {
    .container-about-image {
      justify-content: center;
    }

    .container-about-desc {
      padding-top: 5%;
      p:nth-child(1) {
        font-size: 36px;
      }
      p:nth-child(2) {
        font-size: 20px;
      }
    }
  }
}
</style>
