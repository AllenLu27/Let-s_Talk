<template>
  <div class="soul-self-content" :style="styleObject">
    <div>
      <div style="height: 300px;"><!-- header，background picture --></div>
      <soul-self-item :itemData="cellItemOption1"></soul-self-item>
      <soul-self-item :itemData="cellItemOption2"></soul-self-item>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
import { mapMutations } from 'vuex'
import SoulSelfItem from './Item'
export default {
  name: 'SoulSelf',
  components: {
    SoulSelfItem
  },
  data () {
    return {
      styleObject: {
        overflow: 'hidden',
        height: (window.innerHeight - 100) + 'px'
        /* 减去头部和底部的高度，这里的头部不是fixed定位的，跟广场和聊天的不一样 */
      },
      cellItemOption1: {
        icon: 0,
        nickName: '#来自艺术家星球',
        timeStamp: '2018-11-16 19:10:26 晴天',
        imgs: {
          url: [],
          count: 0
        },
        word: 'balabalabala...',
        topic: ' ',
        location: ' ',
        iconHeartCount: 5,
        iconCommentCount: 20,
        iconForwardCount: 2,
        key: 'jdjsfj'
      },
      cellItemOption2: {
        icon: 0,
        nickName: '#来自艺术家星球',
        timeStamp: '2018-10-16 00:19:29',
        imgs: {
          url: [
            './static/photo1.jpg',
            './static/photo1.jpg'
          ],
          count: 2
        },
        word: 'Go LA',
        topic: ' ',
        location: ' ',
        iconHeartCount: 5,
        iconCommentCount: 20,
        iconForwardCount: 2,
        key: 'jdjsfj'
      }
    }
  },
  methods: {
    ...mapMutations(['changeSoulSelfTopY'])
  },
  mounted () {
    this.bScrollContent = new BScroll('.soul-self-content', {click: true, tap: true, probeType: 3})
    this.bScrollContent.on('scrollStart', () => {
      this.bScrollContent.refresh()
    })
    this.bScrollContent.on('scroll', (pos) => {
      this.changeSoulSelfTopY(pos.y)
    })
  }
}
</script>

<style>
</style>
