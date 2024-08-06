<template>
  <div id="home">
    <q-layout
      view="hHh Lpr lff"
      container
      class="rounded-borders fixed-top"
      :style="{ height: drawer ? '100vh' : '90px', zIndex: 99 }"
    >
      <q-header class="text-white my-header">
        <q-toolbar class="row justify-between">
          <q-space v-if="$q.screen.gt.xs" />
          <q-tabs
            v-model="tab"
            v-if="$q.screen.gt.xs"
            active-color="dark"
            indicator-color="dark"
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
  <div style="min-height: 100vh; background-color: #fbff00" id="about"></div>
  <div style="min-height: 100vh; background-color: #51ff00" id="projects"></div>
</template>

<script setup lang="ts">
import { onMounted, ref } from 'vue';
import Typed from 'typed.js';

const typedStrings =
  'a Designer, an Editor, a Developer, a Freelancer, an Undergraduate'; // This could be dynamic as well

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
</script>

<style scoped>
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
</style>
