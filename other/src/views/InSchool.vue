<template>
  <div id="navRoot">
    <div id="in-school" class="body-w">
      <div class="most-top"></div>
      <div id="live" class="before-component">

        <div id="live-img" class="img"></div>
      </div>
      <div id="eat" class="before-component">

        <div id="eat-img" class="img"></div>
      </div>
      <div id="organization" class="before-component">

        <div id="organization-img" class="img"></div>
      </div>
      <div id="association" class="before-component">

        <div id="association-img" class="img"></div>
      </div>
      <div id="activity" class="before-component">

        <div id="activity-img" class="img"></div>
      </div>
      <div id="convenience" class="before-component">

        <div id="convenience-img" class="img">
          <button id="toNext" class="button-animation" @click="jump">
            <span>
              校外生活&nbsp;&nbsp;
              <i></i>
            </span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Banner from '../components/Banner'
export default {
  name: 'InSchool',
  components: {
    Banner
  },
  data () {
    return {
      publicPath: process.env.BASE_URL
    }
  },
  methods: {
    jump () {
      this.$router.push({ path: '/shool_preparation' })
    },
    getTop () {
      var offTop = []
      offTop[0] = 0
      offTop[1] = document.getElementById('eat').offsetTop
      offTop[2] = document.getElementById('organization').offsetTop
      offTop[3] = document.getElementById('association').offsetTop
      offTop[4] = document.getElementById('activity').offsetTop
      offTop[5] = document.getElementById('convenience').offsetTop
      return offTop
    }
  }
}
</script>

<style scoped>
#in-school img {
  float: right;
  height: 200px;
  margin: 35px;
  border-radius: 8px;
}

#live-img {
  background-image: url(http://bkzs.sxu.edu.cn/images/2019-07/a74bf07dd058456f9215d79e60e835fa.png);
}
#eat-img {
  background-image: url(http://bkzs.sxu.edu.cn/images/2019-07/23eff60137424deca85dcaaef6f8a7c2.jpg);
}
#organization-img {
  background-image: url(http://bkzs.sxu.edu.cn/images/2019-07/aa98b8197576490f9c017e14a8ab78a4.jpg);
}
#association-img {
  background-image: url(http://bkzs.sxu.edu.cn/images/2019-07/c05b9516118f4a24bb6cf69caf57e9dd.jpg);
}
#activity-img {
  background-image: url(http://bkzs.sxu.edu.cn/images/2019-07/bfb28483a8654de3854c4f5cadf3f542.jpg);
}
#convenience-img {
  background-image: url(http://bkzs.sxu.edu.cn/images/2019-07/5c600eade70b433f9e0aec9bce0ab91d.jpg);
}

#live::before {
  content: "住在山大";
}
#eat::before {
  content: "吃在山大";
}
#organization::before {
  content: "学生组织";
}
#association::before {
  content: "多彩社团";
}
#activity::before {
  content: "大型活动";
}
#convenience::before {
  content: "便利生活";
}
</style>
