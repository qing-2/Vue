<template>
  <div class="body-w">
    <div class="con">
      <div class="h_one">留言板</div>
      <div class="comment">
        <div class="vpanel">
          <div class="vwrap">
            <div class="vheader">
              <input name="nick" placeholder="昵称" class="vinput" type="text" v-model="nickname" />
            </div>
            <div class="vedit">
              <textarea id="veditor" class="veditor vinput" placeholder="畅所欲言" v-model="value"></textarea>
              <div class="vrow">
                <div class="vcol vcol-40 vctrl text-left">
                  <span title="表情" class="vicon vemoji-btn">
                    <svg
                      viewBox="0 0 1024 1024"
                      version="1.1"
                      xmlns="http://www.w3.org/2000/svg"
                      p-id="16172"
                      width="22"
                      height="22"
                      @click="showEmojisF"
                    >
                      <path
                        d="M512 1024a512 512 0 1 1 512-512 512 512 0 0 1-512 512zM512 56.888889a455.111111 455.111111 0 1 0 455.111111 455.111111 455.111111 455.111111 0 0 0-455.111111-455.111111zM312.888889 512A85.333333 85.333333 0 1 1 398.222222 426.666667 85.333333 85.333333 0 0 1 312.888889 512z"
                        p-id="16173"
                      />
                      <path
                        d="M512 768A142.222222 142.222222 0 0 1 369.777778 625.777778a28.444444 28.444444 0 0 1 56.888889 0 85.333333 85.333333 0 0 0 170.666666 0 28.444444 28.444444 0 0 1 56.888889 0A142.222222 142.222222 0 0 1 512 768z"
                        p-id="16174"
                      />
                      <path
                        d="M782.222222 391.964444l-113.777778 59.733334a29.013333 29.013333 0 0 1-38.684444-10.808889 28.444444 28.444444 0 0 1 10.24-38.684445l113.777778-56.888888a28.444444 28.444444 0 0 1 38.684444 10.24 28.444444 28.444444 0 0 1-10.24 36.408888z"
                        p-id="16175"
                      />
                      <path
                        d="M640.568889 451.697778l113.777778 56.888889a27.875556 27.875556 0 0 0 38.684444-10.24 27.875556 27.875556 0 0 0-10.24-38.684445l-113.777778-56.888889a28.444444 28.444444 0 0 0-38.684444 10.808889 28.444444 28.444444 0 0 0 10.24 38.115556z"
                        p-id="16176"
                      />
                    </svg>
                  </span>
                </div>
              </div>
            </div>
            <div class="vemojis" style="display: block;" v-show="showEmojis">
              <i title="smile">
                <img
                  alt=":smile:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/e3/2018new_weixioa02_org.png"
                />
              </i>
              <i title="lovely">
                <img
                  alt=":lovely:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/09/2018new_keai_org.png"
                />
              </i>
              <i title="happy">
                <img
                  alt=":happy:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/1e/2018new_taikaixin_org.png"
                />
              </i>
              <i title="clap">
                <img
                  alt=":clap:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/6e/2018new_guzhang_thumb.png"
                />
              </i>
              <i title="whee">
                <img
                  alt=":whee:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/33/2018new_xixi_thumb.png"
                />
              </i>
              <i title="haha">
                <img
                  alt=":haha:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/8f/2018new_haha_thumb.png"
                />
              </i>
              <i title="laugh and cry">
                <img
                  alt=":laugh and cry:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/4a/2018new_xiaoku_thumb.png"
                />
              </i>
              <i title="wink">
                <img
                  alt=":wink:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/43/2018new_jiyan_org.png"
                />
              </i>
              <i title="greddy">
                <img
                  alt=":greddy:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/fa/2018new_chanzui_org.png"
                />
              </i>
              <i title="awkward">
                <img
                  alt=":awkward:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/a3/2018new_heixian_thumb.png"
                />
              </i>
              <i title="sweat">
                <img
                  alt=":sweat:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/28/2018new_han_org.png"
                />
              </i>
              <i title="pick nose">
                <img
                  alt=":pick nose:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/9a/2018new_wabi_thumb.png"
                />
              </i>
              <i title="hum">
                <img
                  alt=":hum:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/7c/2018new_heng_thumb.png"
                />
              </i>
              <i title="angry">
                <img
                  alt=":angry:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/f6/2018new_nu_thumb.png"
                />
              </i>
              <i title="grievance">
                <img
                  alt=":grievance:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/a5/2018new_weiqu_thumb.png"
                />
              </i>
              <i title="poor">
                <img
                  alt=":poor:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/96/2018new_kelian_org.png"
                />
              </i>
              <i title="disappoint">
                <img
                  alt=":disappoint:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/aa/2018new_shiwang_thumb.png"
                />
              </i>
              <i title="sad">
                <img
                  alt=":sad:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/ee/2018new_beishang_org.png"
                />
              </i>
              <i title="tear">
                <img
                  alt=":tear:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/6e/2018new_leimu_org.png"
                />
              </i>
              <i title="no way">
                <img
                  alt=":no way:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/83/2018new_kuxiao_org.png"
                />
              </i>
              <i title="shy">
                <img
                  alt=":shy:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/c1/2018new_haixiu_org.png"
                />
              </i>
              <i title="dirt">
                <img
                  alt=":dirt:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/10/2018new_wu_thumb.png"
                />
              </i>
              <i title="love you">
                <img
                  alt=":love you:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/f6/2018new_aini_org.png"
                />
              </i>
              <i title="kiss">
                <img
                  alt=":kiss:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/2c/2018new_qinqin_thumb.png"
                />
              </i>
              <i title="amorousness">
                <img
                  alt=":amorousness:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/9d/2018new_huaxin_org.png"
                />
              </i>
              <i title="longing">
                <img
                  alt=":longing:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/c9/2018new_chongjing_org.png"
                />
              </i>
              <i title="desire">
                <img
                  alt=":desire:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/3e/2018new_tianping_thumb.png"
                />
              </i>
              <i title="bad laugh">
                <img
                  alt=":bad laugh:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/4d/2018new_huaixiao_org.png"
                />
              </i>
              <i title="blackness">
                <img
                  alt=":blackness:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/9e/2018new_yinxian_org.png"
                />
              </i>
              <i title="laugh without word">
                <img
                  alt=":laugh without word:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/2d/2018new_xiaoerbuyu_org.png"
                />
              </i>
              <i title="titter">
                <img
                  alt=":titter:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/71/2018new_touxiao_org.png"
                />
              </i>
              <i title="cool">
                <img
                  alt=":cool:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/c4/2018new_ku_org.png"
                />
              </i>
              <i title="not easy">
                <img
                  alt=":not easy:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/aa/2018new_bingbujiandan_thumb.png"
                />
              </i>
              <i title="think">
                <img
                  alt=":think:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/30/2018new_sikao_org.png"
                />
              </i>
              <i title="question">
                <img
                  alt=":question:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/b8/2018new_ningwen_org.png"
                />
              </i>
              <i title="no idea">
                <img
                  alt=":no idea:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/2a/2018new_wenhao_thumb.png"
                />
              </i>
              <i title="dizzy">
                <img
                  alt=":dizzy:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/07/2018new_yun_thumb.png"
                />
              </i>
              <i title="bomb">
                <img
                  alt=":bomb:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/a2/2018new_shuai_thumb.png"
                />
              </i>
              <i title="bone">
                <img
                  alt=":bone:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/a1/2018new_kulou_thumb.png"
                />
              </i>
              <i title="be quiet">
                <img
                  alt=":be quiet:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/b0/2018new_xu_org.png"
                />
              </i>
              <i title="shut up">
                <img
                  alt=":shut up:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/62/2018new_bizui_org.png"
                />
              </i>
              <i title="stupid">
                <img
                  alt=":stupid:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/dd/2018new_shayan_org.png"
                />
              </i>
              <i title="surprise ">
                <img
                  alt=":surprise :"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/49/2018new_chijing_org.png"
                />
              </i>
              <i title="vomit">
                <img
                  alt=":vomit:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/08/2018new_tu_org.png"
                />
              </i>
              <i title="cold">
                <img
                  alt=":cold:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/40/2018new_kouzhao_thumb.png"
                />
              </i>
              <i title="sick">
                <img
                  alt=":sick:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/3b/2018new_shengbing_thumb.png"
                />
              </i>
              <i title="bye">
                <img
                  alt=":bye:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/fd/2018new_baibai_thumb.png"
                />
              </i>
              <i title="look down on">
                <img
                  alt=":look down on:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/da/2018new_bishi_org.png"
                />
              </i>
              <i title="white eye">
                <img
                  alt=":white eye:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/ef/2018new_landelini_org.png"
                />
              </i>
              <i title="left hum">
                <img
                  alt=":left hum:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/43/2018new_zuohengheng_thumb.png"
                />
              </i>
              <i title="right hum">
                <img
                  alt=":right hum:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/c1/2018new_youhengheng_thumb.png"
                />
              </i>
              <i title="crazy">
                <img
                  alt=":crazy:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/17/2018new_zhuakuang_org.png"
                />
              </i>
              <i title="scold ">
                <img
                  alt=":scold :"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/87/2018new_zhouma_thumb.png"
                />
              </i>
              <i title="hit on face">
                <img
                  alt=":hit on face:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/cb/2018new_dalian_org.png"
                />
              </i>
              <i title="wow">
                <img
                  alt=":wow:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/ae/2018new_ding_org.png"
                />
              </i>
              <i title="fan">
                <img
                  alt=":fan:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/86/2018new_hufen02_org.png"
                />
              </i>
              <i title="money">
                <img
                  alt=":money:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/a2/2018new_qian_thumb.png"
                />
              </i>
              <i title="yawn">
                <img
                  alt=":yawn:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/55/2018new_dahaqian_org.png"
                />
              </i>
              <i title="sleepy">
                <img
                  alt=":sleepy:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/3c/2018new_kun_thumb.png"
                />
              </i>
              <i title="sleep">
                <img
                  alt=":sleep:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/e2/2018new_shuijiao_thumb.png"
                />
              </i>
              <i title="watermelon ">
                <img
                  alt=":watermelon :"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/01/2018new_chigua_thumb.png"
                />
              </i>
              <i title="doge">
                <img
                  alt=":doge:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/a1/2018new_doge02_org.png"
                />
              </i>
              <i title="dog">
                <img
                  alt=":dog:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/22/2018new_erha_org.png"
                />
              </i>
              <i title="cat">
                <img
                  alt=":cat:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/7b/2018new_miaomiao_thumb.png"
                />
              </i>
              <i title="thumb">
                <img
                  alt=":thumb:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/e6/2018new_zan_org.png"
                />
              </i>
              <i title="good">
                <img
                  alt=":good:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/8a/2018new_good_org.png"
                />
              </i>
              <i title="ok">
                <img
                  alt=":ok:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/45/2018new_ok_org.png"
                />
              </i>
              <i title="yeah">
                <img
                  alt=":yeah:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/29/2018new_ye_thumb.png"
                />
              </i>
              <i title="shack hand">
                <img
                  alt=":shack hand:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/e9/2018new_woshou_thumb.png"
                />
              </i>
              <i title="bow">
                <img
                  alt=":bow:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/e7/2018new_zuoyi_org.png"
                />
              </i>
              <i title="come">
                <img
                  alt=":come:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/42/2018new_guolai_thumb.png"
                />
              </i>
              <i title="punch">
                <img
                  alt=":punch:"
                  referrerpolicy="no-referrer"
                  class="vemoji"
                  src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/86/2018new_quantou_thumb.png"
                />
              </i>
            </div>
            <el-row>
              <el-button plain size='small' @click="createCard">朴素按钮</el-button>
            </el-row>
          </div>
        </div>
        <div class="vcount" style="display: block;">
          <span class="vnum">{{count}}</span> 评论
        </div>
        <div class="vcards" >
          <ul>
            <li :v-for="item in cards"></li>
          </ul>
          <div class="vcard" :v-for="item in cards" :key="item">
            <!-- {{item.value}} -->
            <img
              class="vimg"
              src="https://hbimg.huabanimg.com/1d05cb2318ea720e6e403822500f952d1db5bbac1239-4sGnTf_fw658/format/webp"
            />
            <div class="vh">
              <div class="vnick"></div>
              <div class="vtime">2020-08-19</div>
              <div class="vmeta">
                <div class="vcontent">
                  <p></p>
                </div>
                <span
                  class="vat"
                  data-vm-id="5f37c2e93f1948000669718e"
                  data-self-id="5f37c2e93f1948000669718e"
                >回复</span>
                <div class="vquote" data-self-id="5ef9c0e9dd14020009358938">
                  <div class="vcard" id="5efbbfc5fd84ef0008415f2f">
                    <img
                      class="vimg"
                      src="https://gravatar.loli.net/avatar/d41d8cd98f00b204e9800998ecf8427e?d=monsterid&amp;v=1.4.9"
                    />
                    <div class="vh">
                      <div class="vhead">
                        <span class="vnick">Ganto</span>
                        <span class="vsys">XiaoMi 12.4.10</span>
                        <span class="vsys">Android 8.1.0</span>
                      </div>
                      <div class="vmeta">
                        <span class="vtime">2020-07-01</span>
                        <span
                          class="vat"
                          data-vm-id="5ef9c0e9dd14020009358938"
                          data-self-id="5efbbfc5fd84ef0008415f2f"
                        >回复</span>
                      </div>
                      <div class="vcontent" data-expand="查看更多...">
                        <p>
                          <a class="at" href="#5ef9c0e9dd14020009358938">@loya</a> , 在备考
                          <img
                            alt=":no way:"
                            class="vemoji"
                            referrerpolicy="no-referrer"
                            src="//img.t.sinajs.cn/t4/appstyle/expression/ext/normal/83/2018new_kuxiao_org.png"
                          />
                        </p>
                      </div>
                      <div class="vreply-wrapper" data-self-id="5efbbfc5fd84ef0008415f2f"></div>
                      <div class="vquote" data-self-id="5efbbfc5fd84ef0008415f2f"></div>
                    </div>
                  </div>
                </div>
              </div>

              <div class="vreply-wrapper" data-self-id="5f37c2e93f1948000669718e"></div>
              <div class="vquote" data-self-id="5f37c2e93f1948000669718e"></div>
            </div>
          </div>
<!-- <div :v-for="a in cards">{{a}}</div> -->
        </div>
        <div class="vload-bottom text-center" style="display: none;">
          <i class="vspinner" style="width:30px;height:30px;"></i>
        </div>
        <div class="more" style="display: block;" v-show="count>2">
          <button type="button" class="vbtn">加载更多...</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
function cardObj () {
  return {
    nickname: 'hh',
    value: 'bbb'
  }
}
export default {
  data () {
    return {
      // item: 'i am a item',
      nickname: '',
      value: '',
      showEmojis: 0,
      count: 0,
      // cards: [{ nickname: 'this.nickname', value: 'this.value' }]
      cards: [1, 2, 3, 4, 5]
    }
  },
  components: {},
  methods: {
    showEmojisF () {
      this.showEmojis = !this.showEmojis
    },
    createCard () {
      const card = cardObj()
      this.cards.push(card)
      console.log(this.cards)
      this.count++
    }
  }
  // updated: {
  //   cardObj () {
  //     return {
  //       nickname: 'hh',
  //       value: 'bbb'
  //     }
  //   }
  // }
}

</script>

<style scoped>
* {
  box-sizing: content-box;
  font-family: inherit;
  line-height: 1.75;
}
.vwrap {
  border: 1px solid #e1e4e8;
  border-radius: 4px;
  margin-bottom: 10px;
  position: relative;
  padding: 15px;
  box-sizing: content-box;
}

.con {
  width: 85%;
  border-radius: 5px;
  padding: 0 50px;
  margin: 5px 0px 20px 50px;
}
.h_one {
  display: flex;
  justify-content: center;
  font-size: 24px;
  letter-spacing: 3px;
  padding: 15px;
  font-weight: bold;
}
.vcount {
  padding: 5px;
  font-weight: bold;
  font-size: 1.25em;
}
.veditor {
  width: 100%;
  min-height: 8.75em;
  font-size: 0.875em;
  background: transparent;
  resize: vertical;
  -webkit-transition: all 0.25s ease;
  transition: all 0.25s ease;
}
.vedit {
  background-image: url(https://hbimg.huabanimg.com/2c1bef1f8c1402fcce81fe4aeb26576e0e44716aa546-kwYFEc_fw658/format/webp);
  background-position: right;
  background-size: 60%;
  background-repeat: no-repeat;
}
.vinput {
  border: none;
  resize: none;
  outline: none;
  padding: 10px 5px;
  max-width: 100%;
  font-size: 16px;
}
.vrow {
  padding: 10px 0;
}
.more {
  text-align: center;
}
.vbtn {
  -webkit-transition-duration: 0.4s;
  transition-duration: 0.4s;
  text-align: center;
  color: #313131;
  border: 1px solid #ededed;
  border-radius: 4px;
  display: inline-block;
  background: transparent;
  margin-bottom: 0;
  vertical-align: middle;
  -ms-touch-action: manipulation;
  touch-action: manipulation;
  cursor: pointer;
  white-space: nowrap;
  padding: 0.5em 1.25em;
  font-size: 0.875em;
}
.vwrap .vheader .vinput {
  width: 100%;
  border-bottom: 1px dashed #dedede;
}
.vwrap .vemojis {
  display: none;
  font-size: 18px;
  text-align: justify;
  max-height: 145px;
  overflow: auto;
  padding-bottom: 10px;
  -webkit-box-shadow: 0 0 1px #f0f0f0;
  box-shadow: 0 0 1px #f0f0f0;
}
.vemoji {
  max-height: 28px;
  vertical-align: middle;
  margin: 5px;
  display: inline-block;
}
.text-left {
  text-align: left;
  margin-left: 10px;
}
.vcard {
  padding-top: 1.25em;
  position: relative;
  display: block;
}
.vcards .vcard .vimg {
  width: 3.125em;
  height: 3.125em;
  float: left;
  border-radius: 50%;
  margin-right: 0.7525em;
  border: 1px solid #f5f5f5;
}
.vcontent {
  word-wrap: break-word;
  word-break: break-all;
  text-align: justify;
  font-size: 14px;
  line-height: 2;
  position: relative;
  margin-bottom: 15px;
}
.vhead {
  line-height: 1.5;
  margin-top: 0;
}
.vnick {
  position: relative;
  font-size: 0.875em;
  font-weight: 600;
  margin-right: 0.875em;
  cursor: pointer;
  text-decoration: none;
  display: inline-block;
}
.vat {
  font-size: 0.8125em;
  color: rgb(0, 153, 153);
  cursor: pointer;
  float: right;
}
.vtime {
  color: #b3b3b3;
  font-size: 14px;
}
.vquote {
  padding-left: 1em;
  border-left: 1px dashed hsla(0, 0%, 93%, 0.5);
}
</style>
