<!-- <template>
  <div class="soul-self-header">
    <img :style="imgStyleObject" :src="backgroundImg">
    <div class="soul-self-header-more">更多</div>
    <div class="soul-self-header-detail" :style="detailStyleObject">
      <div class="soul-self-header-headicon">
        <img src="@/assets/images/headicon/0.png">
      </div>
      <div class="soul-self-header-nickName"></div>
      <div class="soul-self-header-register-date">11天,11个瞬间</div>
      <div class="soul-self-header-tags">旅行</div>
    </div>
    <div :style="titleStyleObject">我的瞬间</div>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'SoulSelfHeader',
  data () {
    return {
      backgroundImg: './static/photo1.jpg',
      titleOpacity: 0, // "我的瞬间"透明度
      titleY: 320, // “我的瞬间”向上位移的距离
      imgY: 0 // 图片向上位移的距离
    }
  },
  computed: {
    /* 改变图片位移 */
    imgStyleObject: function () {
      return {
        transform: `translateY(${this.imgY}px)`
      }
    },
    /* 改变“详细信息” */
    detailStyleObject: function () {
      return {
        opacity: 1 - this.titleOpacity
      }
    },
    /* 改变“我的瞬间” */
    titleStyleObject: function () {
      return {
        color: '#fff',
        transform: `translateY(${this.titleY}px)`,
        opacity: this.titleOpacity
      }
    },
    ...mapState(['soulSelf'])
  },
  watch: {
    'soulSelf.topY': function (newValue) {
      if (newValue <= 0 && newValue > -310) {
        this.titleOpacity = Math.abs(newValue / -310)
        this.titleY = 320 + newValue
        this.imgY = newValue * 0.4
      }
    }
  }
}
</script>

<style>
.soul-self-header {
  height: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.soul-self-header img {
  position: absolute;
  width: 100%;
  height: 8rem;
}
.soul-self-header-more {
  position: absolute;
  top: 20px;
  right: 25px;
  color: #fff;
}
.soul-self-header-detail {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.soul-self-header-headicon {
  position: absolute;
  top: 80px;
  width: 50px;
  height: 50px;
  border-radius: 50px;
  background-color: #fff;
}
.soul-self-header-headicon img {
  width: 50px;
  height: 50px;
}
.soul-self-header-nickName {
  position: absolute;
  top: 160px;
  color: #fff;
}
.soul-self-header-register-date {
  position: absolute;
  top: 200px;
  color: #fff;
}
.soul-self-header-tags {
  position: absolute;
  top: 240px;
  height: 0.34rem;
  line-height: 0.34rem;
  border: 1px solid gray;
  border-radius: 0.24rem;
  font-size: 0.24rem;
  color: #fff;
  background-color: rgba(0, 0, 0, 0.4);
}
</style> -->
