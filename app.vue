<template>
  <div class="index-container flex">
    <!-- Preloader Screen -->
    <div v-if="showPreloader">
      <div class="w-screen h-screen flex items-center justify-center relative">
        <div class="w-[70%] md:w-[50%] relative">
          <img 
            src="./dreaming2_files/Preloader.webp" 
            class="w-full"
          />
          <div class="absolute inset-0 flex items-center justify-center">
            <div class="w-[20%] ml-[15%]">
              <img 
                src="./dreaming2_files/cat_sleep.webp" 
                class="w-full"
              />
            </div>
            <div class="w-[60%] ml-[5%] text-[4vw] md:text-[2.5vw] tracking-[.3vw] leading-[3vw] md:leading-[2vw] text-black text-left">
              You are still dreaming.<br />
              Would you like to wake up?
              <div class="mt-[2vw] h-[5vw]">
                <div class="flex">
                  <div 
                    v-for="option in preloaderOptions" 
                    :key="option"
                    @click="handlePreloaderClick"
                    class="text-[3vw] md:text-[3vw] mr-[4vw] md:mr-[3vw] hover:scale-110 cursor-pointer border-[.2vw] border-black px-[1vw] py-[.3vw]"
                  >
                    {{ option }}
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Main Content -->
    <div v-else class="flex">
      <!-- Sidebar -->
      <div class="w-[7vw] md:w-[4.5vw] bg-[#89F6DB] h-screen items-center flex flex-col">
        <div 
          v-for="icon in sidebarIcons" 
          :key="icon.name"
          class="pt-[2vw] md:pt-[.5vw] pb-[3vw] md:pb-[1vw] h"
        >
          <img 
            :src="icon.src" 
            :class="icon.class"
            @click="icon.action"
          />
        </div>
      </div>

      <!-- Main Area -->
      <div class="w-[93vw] md:w-[95.5vw] h-[97vh] md:h-screen relative">
        <!-- Contract Address -->
        <div class="text-[#00FF00] text-[4.5vw] ml-[10vw] md:text-[3vw] tracking-[.5vw] md:tracking-[.4vw] pt-[2vw] md:pt-0 justify-center flex w-100">
          CA : DWDLjUfkMb9xCku4goF6YiSj7xnNrByQ89FLfdqboop
        </div>

        <!-- Left Side Icons -->
        <div class="flex flex-col w-[7vw] ml-2 md:ml-5 md:w-[3.5vw] gap-y-[3vw] md:gap-y-[2vw] mt-[-5vw] md:mt-[-2vw]">
          <img src="./dreaming2_files/Nintendo64.webp" />
          <img src="./dreaming2_files/ExplorerGif.gif" />
          <img src="./dreaming2_files/DiskGif.gif" />
          <img src="./dreaming2_files/HeartGif2.gif" />
          <img src="./dreaming2_files/ToiletGif.gif" />
          <img src="./dreaming2_files/PSImg.webp" />
        </div>

        <!-- Center Content -->
        <div class="gap-y-[6vh] flex items-center justify-center flex-col absolute w-full bottom-[10vh] md:bottom-[.5vw]">
          <img 
            src="./dreaming2_files/StatueFace.webp" 
            class="h-[30vh] md:h-[45vh]"
          />
          <div class="space-y-[-36vh] md:space-y-[-44vh] flex flex-col items-center">
            <img 
              src="./dreaming2_files/buy_button.webp" 
              class="bounce-7 h-[15vh] md:h-[18vh] z-[99] cursor-pointer hover:scale-110"
              @click="handleBuyClick"
            />
            <div class="space-y-[-19vh] md:space-y-[-23vh] flex flex-col items-center">
              <img 
                src="./dreaming2_files/MainIcon.webp" 
                class="h-[40vh] md:h-[50vh] z-[5]"
              />
              <img 
                src="./dreaming2_files/PillarGif.gif" 
                class="h-[30vh] md:h-[28vh] z-0"
              />
            </div>
          </div>
        </div>

        <!-- Floating Elements Top -->
        <div class="absolute w-full pl-[5vw] md:pl-0 top-[8vw] md:top-[3.5vw]">
          <div>
            <img src="./dreaming2_files/Tab1.webp" class="tab-popup absolute w-[35vw] md:w-[25vw] left-[10vw] md:left-[7vw] z-0" />
            <img src="./dreaming2_files/PinkCatGif.gif" class="tab-popup absolute w-[35vw] md:w-[10vw] top-[5vw] left-[11vw] md:left-[10vw] z-0" />
            <img src="./dreaming2_files/AnythingCanHappenGif.gif" class="tab-popup absolute w-[35vw] md:w-[11vw] top-[3vw] left-[10vw] md:left-[18vw] z-0" />
          </div>
          <img src="./dreaming2_files/Tab2Gif.gif" class="tab-popup absolute w-[25vw] md:w-[18vw] left-[20vw] top-[14vw] z-[1]" />
          <img src="./dreaming2_files/Tab3.webp" class="tab-popup absolute w-[15vw] md:w-[15vw] left-[32vw] md:left-[26vw] top-[3vw] z-[5]" />
          <div>
            <img src="./dreaming2_files/AnimeGif.gif" class="tab-popup absolute w-[20vw] md:w-[20vw] right-[32vw] md:right-[23vw] top-[25.5vw] md:top-[10.5vw] z-10" />
            <img src="./dreaming2_files/Tab4.webp" class="tab-popup absolute w-[13vw] md:w-[13vw] right-[35vw] md:right-[26vw] top-[36.5vw] md:top-[21.5vw] z-10" />
          </div>
          <img src="./dreaming2_files/Tab5.webp" class="tab-popup absolute w-[20vw] md:w-[15vw] right-[18vw] md:right-[13vw] top-[33vw] md:top-[20vw] z-[5]" />
          <img src="./dreaming2_files/HandHeartImage.webp" class="absolute w-[20vw] md:w-[13vw] right-0 top-[36vw] md:top-[23vw] z-0" />
          <img src="./dreaming2_files/Tab6Gif.gif" class="tab-popup absolute w-[35vw] md:w-[22vw] right-[.5vw] top-[.5vw] z-0" />
          <img src="./dreaming2_files/DolphinGif.gif" class="absolute w-[25vw] md:w-[16vw] right-[25vw] top-[-2vw] z-0" />
          <img src="./dreaming2_files/SadHeartGif.gif" class="absolute w-[7vw] right-[33vw] md:right-[21vw] top-[24vw] md:top-[13vw] z-0" />
          <img src="./dreaming2_files/JapaneseWordGif.gif" class="absolute w-[20vw] md:w-[15vw] right-[30vw] top-[15vw] md:top-[6vw] z-0" />
        </div>

        <!-- Floating Elements Bottom -->
        <div class="absolute w-full bottom-0 pl-[5vw] md:pl-0 top-[10vw] md:top-[3vw]">
          <img src="./dreaming2_files/StarGif.gif" class="absolute w-[15vw] md:w-[8vw] left-[11vw] top-[40vw] md:top-[21vw]" />
          <img src="./dreaming2_files/StatueGif.gif" class="absolute w-[35vw] md:w-[13vw] left-0 md:left-[5vw] bottom-0" />
          <img src="./dreaming2_files/IcecreamGif.gif" class="absolute w-[15vw] md:w-[7vw] left-[23vw] md:left-[15vw] bottom-0" />
          <img src="./dreaming2_files/WindowsImg.webp" class="absolute w-[11vw] md:w-[7vw] left-[35vw] md:left-[28vw] bottom-[1vw]" />
          <img src="./dreaming2_files/japaneseword.webp" class="absolute w-[25vw] md:w-[9vw] left-[35vw] md:left-[22vw] bottom-[13vw] md:bottom-[3vw] z-0" />
          <img src="./dreaming2_files/SadFaceGif.gif" class="absolute w-[13vw] md:w-[10vw] left-[43vw] md:left-[35vw] bottom-0 z-0" />
          <img src="./dreaming2_files/PowerGif.gif" class="absolute w-[40vw] md:w-[15vw] right-0 md:right-[25vw] bottom-0 z-0" />
          <img src="./dreaming2_files/GameboyGif.gif" class="absolute w-[15vw] md:w-[8vw] right-[3vw] md:right-[15vw] bottom-[40vw] md:bottom-[3vw] z-0" />
        </div>
      </div>
    </div>

    <!-- Audio -->
    <audio ref="audioPlayer" loop preload="auto">
      <source src="./dreaming2_files/MidnightPretenders.B4DeZdXM.mp3" type="audio/mp3" />
      Your browser does not support the audio element.
    </audio>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const showPreloader = ref(true)
const audioPlayer = ref(null)
const isPlaying = ref(false)

const preloaderOptions = ['No', "No I wouldn't"]

const sidebarIcons = [
  {
    name: 'unmute',
    src: './dreaming2_files/unmute.webp',
    class: 'w-[6vw] md:w-[3.5vw] p-[.5vw] px-[.5vw] cursor-pointer hover:scale-110',
    action: toggleAudio
  },
  {
    name: 'twitter',
    src: './dreaming2_files/twitter.gif',
    class: 'w-[6vw] md:w-[3.5vw] p-[.5vw] px-[.5vw] cursor-pointer hover:scale-110',
    action: () => window.open('https://twitter.com', '_blank')
  },
  {
    name: 'dex',
    src: './dreaming2_files/dex.webp',
    class: 'w-[6vw] md:w-[3.5vw] p-[.5vw] px-[.5vw] cursor-pointer hover:scale-110',
    action: () => console.log('Dex clicked')
  }
]

function handlePreloaderClick() {
  showPreloader.value = false
}

function handleBuyClick() {
  console.log('Buy button clicked')
}

function toggleAudio() {
  if (audioPlayer.value) {
    if (isPlaying.value) {
      audioPlayer.value.pause()
    } else {
      audioPlayer.value.play()
    }
    isPlaying.value = !isPlaying.value
  }
}

onMounted(() => {
  // Auto-hide preloader after 3 seconds if user doesn't interact
  setTimeout(() => {
    if (showPreloader.value) {
      showPreloader.value = false
    }
  }, 3000)
})
</script>

<style scoped>
.index-container {
  background-image: url('./dreaming2_files/Backdrop.webp');
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  font-family: 'windows-xp-tahoma';
  height: 100vh;
  width: 100%;
}

/* Loading spinner */
.donut-spinner {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  background: conic-gradient(#00d91d 0%, #039a79 20%, #05b6d3 40%, #2401fe 60%, #0d85df 80%, #ff00fd 100%);
  mask: radial-gradient(farthest-side, transparent 60%, white 0);
  -webkit-mask: radial-gradient(farthest-side, transparent 60%, white 0);
  animation: spin 1s linear infinite;
}

/* Kreep animation */
.animate-kreep {
  animation: kreep 0.8s ease 2s infinite alternate;
}

@keyframes kreep {
  0% { transform: scale(1.1, 0.9); }
  40% { -webkit-transform: scale(0.9, 1.1) translateY(-0.5rem); }
  70% { transform: scale(1); }
}

/* Bounce animation */
.bounce-7 {
  animation-name: bounce-7;
  animation-duration: 1.5s;
  animation-iteration-count: infinite;
  animation-timing-function: cubic-bezier(0.28, 0.84, 0.42, 1);
}

@keyframes bounce-7 {
  0% { transform: scale(1, 1) translateY(0); }
  10% { transform: scale(1.1, 0.9) translateY(0); }
  30% { transform: scale(0.9, 1.1) translateY(-50px); }
  50% { transform: scale(1.05, 0.95) translateY(0); }
  57% { transform: scale(1, 1) translateY(-7px); }
  64% { transform: scale(1, 1) translateY(0); }
  100% { transform: scale(1, 1) translateY(0); }
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

/* Popup animation */
@keyframes popup {
  0% { opacity: 0; transform: scale(0.8); }
  100% { opacity: 1; transform: scale(1); }
}

.tab-popup {
  animation: popup 0.6s ease-out;
  transition: transform 1s ease-in-out, opacity 1s ease-in-out;
}

.tab-popup:hover {
  transform: scale(1.1);
}

/* Loading container */
.loading-container {
  display: flex;
  justify-content: flex-start;
  align-items: center;
}

.pixel {
  width: 2.5vw;
  height: 2.5vw;
  background-color: white;
}

.active {
  background: #00d91d;
  background: linear-gradient(260deg, #00d91d 0%, #039a79 21%, #05b6d3 35%, #0d85df 51%, #2401fe 67%, #ff00fd 95%);
}
</style>
