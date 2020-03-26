<template>
  <div id="app">
    <div class="grid-layout-containert">
      <grid-layout
                  ref="layout1"
                  :layout="layoutLeft"
                  :col-num="6"
                  :is-draggable="false"
                  :is-resizable="false"
                  :is-mirrored="true"
                  :vertical-compact="true"
                  :margin="[0, 0]"
                  :use-css-transforms="true"
      >
        <grid-item v-for="item in layoutLeft"
                   :x="item.x"
                   :y="item.y"
                   :w="item.w"
                   :h="item.h"
                   :i="item.i"
                   :key="item.i">
          <div class="container">
            <MetroTile
                :width="item.w*(gridLayoutWidth/6)"
                :height="item.h*(gridLayoutHeight)"
                :length="item.length"
                :rotateX="item.rotateX"
                :faceStyle="item.faceStyle">
              <!-- custom face for each tile in left layout-->
              <template >
                <div slot="front">
                    <div class="tile-label">
                      Microsoft Store
                    </div>
                    <img src="https://user-images.githubusercontent.com/6414178/45696034-3fd14280-bb95-11e8-8c45-cd2020fabefc.png" class="store-cover-img" />
                    <div class="store-title">
                      Cyberpunk 2077
                    </div>
                    <div class="store-subtitle">
                        Free&#8314;
                    </div>
                    <StoreIcon style="fill: white" class="store-icon-right"/>
                </div>
                <div slot="top">
                    <div class="tile-label">
                      Microsoft Store
                    </div>
                    <img src="https://user-images.githubusercontent.com/6414178/45696084-56779980-bb95-11e8-87ac-817bf448cd4f.png" class="store-cover-img" />
                    <div class="store-title">
                      Half-Life 3: Episode 1
                    </div>
                    <div class="store-subtitle">
                        Free&#8314;
                    </div>
                    <StoreIcon style="fill: white" class="store-icon-right"/>
                </div>
                <div slot="bottom">
                    <div class="tile-label">
                      Microsoft Store
                    </div>
                    <img src="https://user-images.githubusercontent.com/6414178/45696072-4eb7f500-bb95-11e8-8e7c-ccb0099e5161.png" class="store-cover-img" />
                    <div class="store-title">
                      Grand Theft Auto VI
                    </div>
                    <div class="store-subtitle">
                        Free&#8314;
                    </div>
                    <StoreIcon style="fill: white" class="store-icon-right"/>
                </div>
              </template>
            </MetroTile>
          </div>
        </grid-item>
      </grid-layout>
    </div>
  </div>
</template>

<script>
import MetroTile from './components/MetroTile.vue'
import VueGridLayout from 'vue-grid-layout';
import EdgeIcon from './assets/edge.svg';
import XboxIcon from './assets/xbox.svg';
import OfficeIcon from './assets/office.svg';
import OneNoteIcon from './assets/oneNote.svg';
import PowerPointIcon from './assets/powerPoint.svg';
import CortanaIcon from './assets/cortana.svg';
import StoreIcon from './assets/store.svg';
import WeatherIcon from './assets/weather.svg';
import SettingsIcon from './assets/settings.svg';
import PhotoIcon from './assets/photo.svg';
import CameraIcon from './assets/camera.svg';
import ExcelIcon from './assets/excel.svg';
import GithubIcon from './assets/github.svg';
import GrooveIcon from './assets/groove.svg';
import ChromeIcon from './assets/chrome.svg';
import AccessIcon from './assets/access.svg';

const BASE_LEN = 100;
const MARGIN = 3;
const REPO_URL = 'https://github.com/yuanfux/vue-metro-tile';

export default {
  name: 'app',
  components: {
    MetroTile,
    VueGridLayout,
    EdgeIcon,
    XboxIcon,
    OfficeIcon,
    OneNoteIcon,
    PowerPointIcon,
    CortanaIcon,
    StoreIcon,
    WeatherIcon,
    SettingsIcon,
    PhotoIcon,
    CameraIcon,
    ExcelIcon,
    GithubIcon,
    GrooveIcon,
    ChromeIcon,
    AccessIcon
  },
  data: () => ({
      gridLayoutWidth:100,
      gridLayoutHeight:100,
    BASE_LEN,
    layoutLeft: [
      {
        x: 0,
        y: 0,
        w: 4,
        h: 2,
        i: "0",
        rotateX: 0,
        faceStyle: {
          'background-color': '#1E90FF'
        }
       },
      {
        x: 2,
        y: 2,
        w: 4,
        h: 2,
        i: "1",
        rotateX: 0,
        faceStyle: {
          'background-color': '#228b22'
        }
      },
      {
        x: 0,
        y: 4,
        w: 4,
        h: 2,
        i: "2",
        rotateX: 0,
        faceStyle: {
          'background-color': '#ff4500'
        }
      },
      {
        x: 4,
        y: 0,
        w: 2,
        h: 2,
        i: "3",
        rotateX: 0,
        faceStyle: {
          'background-color': '#9400d3'
        }
      },
      {
        x: 4,
        y: 4,
        w: 2,
        h: 2,
        i: "4",
        rotateX: 0,
        faceStyle: {
          'background-color': '#ffa07a'
        }
      },
      {
        x: 0,
        y: 2,
        w: 2,
        h: 2,
        i: "5",
        rotateX: 0,
        faceStyle: {
          'background-color': '#1E90FF'
        }
      },
      {
        x: 0,
        y: 6,
        w: 2,
        h: 2,
        i: "6",
        rotateX: 0,
        faceStyle: {
          'background-color': '#1E90FF'
        }
      },
      {
        x: 2,
        y: 6,
        w: 4,
        h: 2,
        i: "7",
        rotateX: 0,
        faceStyle: {
          'background-color': '#1E90FF'
        }
      }
    ],
    layoutRight: [
      {
        x: 0,
        y: 0,
        w: 1,
        h: 1,
        i: "0",
        width: BASE_LEN - MARGIN*2,
        height: BASE_LEN - MARGIN*2,
        rotateX: 0,
        faceStyle: {
          'background-color': '#1E90FF'
        }
      },
      {
        x: 1,
        y: 0,
        w: 1,
        h: 1,
        i: "1",
        width: BASE_LEN - MARGIN*2,
        height: BASE_LEN - MARGIN*2,
        rotateX: 0,
        faceStyle: {
          'background-color': '#1E90FF'
        }
      },
      {
        x: 1,
        y: 1,
        w: 1,
        h: 1,
        i: "2",
        width: BASE_LEN - MARGIN*2,
        height: BASE_LEN - MARGIN*2,
        rotateX: 0,
        faceStyle: {
          'background-color': '#1E90FF'
        }
      },
      {
        x: 0,
        y: 1,
        w: 1,
        h: 1,
        i: "3",
        width: BASE_LEN - MARGIN*2,
        height: BASE_LEN - MARGIN*2,
        rotateX: 0,
        faceStyle: {
          'background-color': '#1E90FF'
        }
      },
      {
        x: 2,
        y: 0,
        w: 4,
        h: 2,
        i: "4",
        width: BASE_LEN*4 - MARGIN*2,
        height: BASE_LEN*2 - MARGIN*2,
        rotateX: 0,
        faceStyle: {
          'background-color': '#3cb371'
        }
      },
      {
        x: 0,
        y: 2,
        w: 4,
        h: 4,
        i: "5",
        width: BASE_LEN*4 - MARGIN*2,
        height: BASE_LEN*4 - MARGIN*2,
        rotateX: 0,
        faceStyle: {
          'background-color': '#000'
        }
      },
      {
        x: 4,
        y: 2,
        w: 2,
        h: 2,
        i: "6",
        width: BASE_LEN*2 - MARGIN*2,
        height: BASE_LEN*2 - MARGIN*2,
        rotateX: 0,
        frontStyle: {
          'background-color': '#8a2be2'
        },
        topStyle: {
          'background-color': '#1E90FF'
        },
        backStyle: {
          'background-color': 'yellow'
        },
        bottomStyle: {
          'background-color': 'green'
        },
        perspective: 0
      },
      {
        x: 4,
        y: 4,
        w: 2,
        h: 2,
        i: "7",
        width: BASE_LEN*2 - MARGIN*2,
        height: BASE_LEN*2 - MARGIN*2,
        rotateX: 0,
        faceStyle: {
          'background-color': '#4169e1'
        }
      },
      {
        x: 0,
        y: 6,
        w: 4,
        h: 2,
        i: "8",
        width: BASE_LEN*4 - MARGIN*2,
        height: BASE_LEN*2 - MARGIN*2,
        rotateX: 0,
        faceStyle: {
          'background-color': '#4169e1'
        }
      },
      {
        x: 4,
        y: 6,
        w: 2,
        h: 2,
        i: "9",
        width: BASE_LEN*2 - MARGIN*2,
        height: BASE_LEN*2 - MARGIN*2,
        rotateX: 0,
        faceStyle: {
          'background-color': '#cd5c5c'
        }
      }
    ],
    weekDay: (() => {
      const weekDayMap = {
        0: 'Sunday',
        1: 'Monday',
        2: 'Tuesday',
        3: 'Wednesday',
        4: 'Thursday',
        5: 'Friday',
        6: 'Saturday'
      }
      return weekDayMap[new Date().getDay()];
    })(),
    monthDay: (() => {
      return new Date().getDate();
    })(),
    rotateIndex1: 0,
    rotateArray1: [-90, 90, 90, -90],
    rotateIndex2: 0,
    rotateArray2: [-90, 90],
  }),
  methods: {
    setRotateX(layoutItem, rotateIndexName, rotateArray) {
      layoutItem.rotateX += rotateArray[this[rotateIndexName] % rotateArray.length];
      this[rotateIndexName] += 1;
    },
    redirect() {
      window.open(REPO_URL, '_blank');
      // window.location.href = REPO_URL;
    }
  },
  mounted() {

    this.interval1 = setInterval(
      () => {
        this.setRotateX(this.layoutLeft[7], 'rotateIndex1', this.rotateArray1);
      }, 3000);
    this.interval2 = setInterval(
      () => {
        this.setRotateX(this.layoutRight[6], 'rotateIndex2', this.rotateArray2);
      }, 5000);
      setTimeout(()=>{
          // this.gridLayoutWidth=this.$refs.layout1.rowHeight
          this.gridLayoutWidth=this.$refs.layout1.width-6
          this.gridLayoutHeight=this.$refs.layout1.rowHeight
  }, 300);
  },
  beforeDestroy() {
    clearInterval(this.interval1);
    clearInterval(this.interval2);
  }
}
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 100vw;
  height: 100vh;
  text-align: center;
}

body {
  background: radial-gradient(circle, rgba(61,82,108,1) 0%, rgba(29,50,75,1) 100%);
}

.title {
  font-family: "Segoe UI", Frutiger, "Frutiger Linotype", "Dejavu Sans", "Helvetica Neue", Arial, sans-serif;
  font-size: 20px;
  font-weight: 500;
  padding: 0 0 10px 0;
  color: #fff;
}

.subtitle {
  font-family: "Segoe UI", Frutiger, "Frutiger Linotype", "Dejavu Sans", "Helvetica Neue", Arial, sans-serif;
  font-size: 17px;
  font-weight: 500;
  padding-bottom: 30px;
  color: #fff;
}

.grid-layout-container {
  display: inline-block;
  width: 100%;
  height: 100%;
}

.margin-right {
  margin-right: 17px
}

.container {
  margin: 3px;
  width: calc(100% - 6px);
  height: calc(100% - 6px);
}

.icon {
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  margin: auto;
}

.image {
  position: absolute;
  width: 50px;
  height: 50px;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  margin: auto;
}

.store-icon-right {
  position: absolute;
  right: 5px;
  bottom: 5px;
  margin: auto;
}

.store-cover-img {
  position: absolute;
  left: 18px;
  top: 10px;
  height: 200px;
  width: 200px;
}

.store-title {
  font-family: "Segoe UI", Frutiger, "Frutiger Linotype", "Dejavu Sans", "Helvetica Neue", Arial, sans-serif;
  font-size: 36px;
  font-weight: 400;
  color: #fff;
  position: absolute;
  top: 10px;
  left: 200px;
}

.store-subtitle {
  font-family: "Segoe UI", Frutiger, "Frutiger Linotype", "Dejavu Sans", "Helvetica Neue", Arial, sans-serif;
  font-size: 14px;
  font-weight: 400;
  color: rgba(255, 255, 255, 0.5);
  position: absolute;
  top: 35px;
  left: 65px;
}

.tile-label {
  font-family: "Segoe UI", Frutiger, "Frutiger Linotype", "Dejavu Sans", "Helvetica Neue", Arial, sans-serif;
  font-size: 24px;
  font-weight: 500;
  color: #fff;
  position: absolute;
  left: 8px;
  bottom: 5px;
}

.vue-grid-item.vue-grid-placeholder {
  background-color: transparent !important;
}

.calendar {
  width: 100%;
  height: 100%;
  position: absolute;
  text-align: center;
  font-family: "Segoe UI", Frutiger, "Frutiger Linotype", "Dejavu Sans", "Helvetica Neue", Arial, sans-serif;
  color: #fff;
}
.calendar .calendar-week-day {
  margin-top: 20px;
  font-size: 14px;
  font-weight: 500;
}

.calendar .calendar-month-day {
  margin-top: 15px;
  font-size: 30px;
  transform: scale(1.75);
}

</style>
