<template>
  <div id="navRoot">
    <div id="enter-school" class="body-w">
      <div class="most-top"></div>
      <div id="welcome" class="before-component">
        <welcome></welcome>
        <div id="welcome-img" class="img"></div>
      </div>
      <div id="wu" class="before-component">
        <wu></wu>
        <div id="wu-img" class="img"></div>
      </div>
      <div id="ddg" class="before-component">
        <ddg></ddg>
        <div id="ddg-img" class="img"></div>
      </div>
      <div id="ds" class="before-component">
        <ds></ds>
        <div id="ds-img" class="img">
          <button id="toNext" class="button-animation" @click="jump">
            <span>
              入学准备&nbsp;&nbsp;
              <i></i>
            </span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import welcome from '../components/EnterSchool/welcome'
import wu from '../components/EnterSchool/wu'
import ddg from '../components/EnterSchool/ddg'
import ds from '../components/EnterSchool/ds'

export default {
  name: 'EnterSchool',
  components: {
    welcome,
    wu,
    ddg,
    ds
  },
  data () {
    return {}
  },
  methods: {
    jump () {
      this.$router.push({ path: '/shool_preparation' })
    },
    getTop () {
      var offTop = []
      offTop[0] = 0
      offTop[1] = document.getElementById('wu').offsetTop
      offTop[2] = document.getElementById('ddg').offsetTop
      offTop[3] = document.getElementById('ds').offsetTop
      return offTop
    }
  }
}
</script>

<style scoped>
#welcome-img {
  background-image: url(http://bkzs.sxu.edu.cn/images/2019-07/a43bb5de8a31408c8003f0873c033112.jpg);
}
#wu-img {
  background-image: url(http://bkzs.sxu.edu.cn/images/2019-07/055eaa596fbf4b8d9339675fd939b0a1.jpg);
}
#ddg-img {
  background-image: url(http://bkzs.sxu.edu.cn/images/2019-07/bcc2be8daaa34e05b292f0aaf26e9ba5.jpg);
}
#ds-img {
  background-image: url(http://bkzs.sxu.edu.cn/images/2019-07/2697caa07b054378829225ef872196f2.jpg);
}

#welcome::before {
  content: "百年山大";
}
#wu::before {
  content: "坞城校区";
}
#ddg::before {
  content: "大东关校区";
}
#ds::before {
  content: "东山校区";
}
</style>
