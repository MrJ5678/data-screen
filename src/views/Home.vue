<template>
  <div class="home">
    <loading v-if="loading">
      <div class="loading-text">数据大屏加载中...</div>
    </loading>
    <container v-else :options="{width: 3840, height: 2160}">
      <div class="header">
        <top-header/>
      </div>
      <div class="separator"/>
      <div class="center">
        <div class="left">
          <div class="left1">
            <total-user
              :today-user="todayUser"
              :growth-last-day="growthLastDay"
              :growth-last-month="growthLastMonth"
            />
          </div>
          <div class="left2">
            <average-age
              :data="ageData"
              :avg-age="averageAge"
            />
          </div>
          <div class="left3">333</div>
          <div class="left4">444</div>
          <div class="left5">555</div>
          <div class="left6">666</div>
        </div>
        <div class="right">
          <div class="right-top1">777</div>
          <div class="right-top2">888</div>
          <div class="right-bottom">
            <div class="right-bottom-left">
              <div class="right-bottom-left1">333</div>
              <div class="right-bottom-left2">222</div>
              <div class="right-bottom-left3">111</div>
              <div class="right-bottom-left4">000</div>
            </div>
            <div class="right-bottom-right">
              <div class="right-bottom-right1">444</div>
              <div class="right-bottom-right2">555</div>
            </div>
          </div>
        </div>
      </div>
    </container>
  </div>
</template>

<script>
import TopHeader from '@/components/TopHeader/'
import TotalUser from '@/components/TotalUser/index'
import AverageAge from '@/components/AverageAge/index'
import useScreenData from '@/hooks/useScreenData'
import { ref } from 'vue'

export default {
  name: 'Home',
  components: {
    AverageAge,
    TopHeader,
    TotalUser
  },
  setup () {
    const loading = ref(false)

    return {
      loading,
      ...useScreenData()
    }
  }
}
</script>

<style lang="scss">
.home {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
  background-color: rgb(29, 29, 29);
  color: #fff;
  font-size: 48px;
  #container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    .header {
      width: 100%;
      height: 167px;
      background-color: yellow;
    }
    .separator {
      width: 100%;
      height: 10px;
      background-color: rgb(92, 88, 89);
    }
    .center {
      width: 100%;
      flex: 1;
      display: flex;
      background-color: rebeccapurple;
      .left {
        flex: 0 0 860px;
        background-color: red;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        padding-bottom: 20px;
        width: 860px;
        height: 100%;
        box-sizing: border-box;
        .left1 {
          height: 300px;
          background-color: green;
        }
        .left2 {
          height: 320px;
          background-color: yellowgreen;
        }
        .left3 {
          height: 280px;
          background-color: blueviolet;
        }
        .left4 {
          height: 230px;
          background-color: mediumpurple;
        }
        .left5 {
          height: 360px;
          background-color: pink;
        }
        .left6 {
          height: 360px;
          background-color: darkred;
        }
      }
      .right {
        flex: 1;
        background-color: blue;
        display: flex;
        flex-direction: column;
        .right-top1 {
          width: 100%;
          height: 206px;
          background-color: darkred;
        }
        .right-top2 {
          width: 100%;
          height: 48px;
          background-color: cadetblue;
        }
        .right-bottom {
          flex: 1;
          display: flex;
          .right-bottom-left {
            flex: 0 0 1917px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            width: 1917px;
            padding-bottom: 20px;
            box-sizing: border-box;
            .right-bottom-left1 {
              height: 999px;
              background-color: red;
            }
            .right-bottom-left2 {
              height: 80px;
              background-color: yellowgreen;
            }
            .right-bottom-left3 {
              height: 350px;
              background-color: deepskyblue;
            }
            .right-bottom-left4 {
              height: 220px;
              background-color: orangered;
            }
          }
          .right-bottom-right {
            flex: 1;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            padding-bottom: 20px;
            margin-left: 10px;
            box-sizing: border-box;
            .right-bottom-right1 {
              width: 100%;
              height: 999px;
              background-color: burlywood;
            }
            .right-bottom-right2 {
              flex: 1;
              width: 100%;
              margin-top: 20px;
              background-color: darkred;
            }
          }
        }
      }
    }
  }
}

.loading-text {
  font-size: 20px;
  margin-top: 10px;
}
</style>
