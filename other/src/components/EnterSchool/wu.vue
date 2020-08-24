<template>
  <div class="text" id="wu-text" v-html="content"></div>
</template>

<script>
import marked from 'marked'
import {
  renderConfigMarked,
  getCheckInfo,
  scrollToChecked
} from '@/utils/marked.utils.js'
import {
  markdown,
  classNames,
  routePath,
  pageName
} from '@/doc/EnterSchool/wu.js'

export default {
  data () {
    return {
      content: '',
      check: '学'
    }
  },
  mounted () {
    const renderer = renderConfigMarked({ pClassName: classNames.pClassName })
    if (this.check !== '') {
      const { html, checkedList } = getCheckInfo(
        renderer,
        markdown,
        this.check,
        routePath,
        classNames.pClassName,
        pageName
      )
      this.content = html
      // 选择第几个
      const checkedIndex = 0
      scrollToChecked(this, checkedList, checkedIndex)
    } else {
      marked.use({ renderer })
      this.content = marked(markdown)
    }
  }
  // updated () {
  //   document.getElementsByClassName('text').style.backgroundColor =
  //     'blueviolet'
  //   document.getElementsByClassName('text').style.a.nthChild = 'blue'
  // }
}
</script>

<style>
#wu-text a {
  margin-left: 80px;
  padding-bottom: 0;
  text-decoration: none;
  /* background-color: blueviolet; */
}
#wu-text >>> a:nth-child(even) {
  color: aqua;
  left: calc(50vw - 70px);
  top: -30px;
  background-color: blueviolet;
}
</style>
