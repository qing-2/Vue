<template>
  <div id="navRoot">
    <div id="school-preparation" class="body-w">
      <div class="most-top"></div>
      <div id="goods" class="before-component">
        <goods></goods>
        <div id="goods-img" class="img"></div>
      </div>
      <div id="process" class="before-component">
        <process></process>
        <div id="process-img" class="img"></div>
      </div>
      <div id="way" class="before-component">
        <way></way>
        <div id="way-img" class="img"></div>
      </div>
      <div id="tip" class="before-component">
        <tip></tip>
        <div id="tip-img" class="img">
          <button id="toNext" class="button-animation" @click="jump">
            <span>
              校内生活&nbsp;&nbsp;
              <i></i>
            </span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import goods from '../components/SchoolPreparation/goods'
import process from '../components/SchoolPreparation/process'
import way from '../components/SchoolPreparation/way'
import tip from '../components/SchoolPreparation/tip'

export default {
  name: 'SchoolPreparation',
  components: {
    goods,
    process,
    way,
    tip
  },
  methods: {
    jump () {
      this.$router.push({ path: '/in_school' })
    },
    getTop () {
      var offTop = []
      offTop[0] = 0
      offTop[1] = document.getElementById('process').offsetTop
      offTop[2] = document.getElementById('way').offsetTop
      offTop[3] = document.getElementById('tip').offsetTop
      return offTop
    }
  },
  data () {
    return {}
  }
}
</script>

<style scoped>
#goods-img {
  background-image: url(http://bkzs.sxu.edu.cn/images/2019-07/d88f160d4fa045b6be772e0293b8e6b0.png);
}
#process-img {
  background-image: url(http://bkzs.sxu.edu.cn/images/2019-07/da6fbf0a34ef419c8bd53576e8e6a33e.jpg);
}
#way-img {
  background-image: url(http://bkzs.sxu.edu.cn/images/2019-07/cddb0207a02e4f7dadf0c8d2ea28b69b.jpg);
}
#tip-img {
  background-image: url(http://bkzs.sxu.edu.cn/images/2019-07/f1f5fb623bfd4bcfa0c1d3646eb6bf89.jpg);
}

#goods::before {
  content: "物品准备";
}
#process::before {
  content: "报到流程";
}
#way::before {
  content: "到校方式";
}
#tip::before {
  content: "军训小贴士";
}
</style>
