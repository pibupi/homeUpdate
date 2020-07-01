<template>
  <div class="tip-wrap">
    <header class="tip-header">
      <span class="tip-header-title">进入控制台组界面</span>
      <p class="tip-header-low">近期代办</p>
    </header>
    <section class="middle">
      <div class="middle-tag">
        <span @click="toggletag(1)">待处理工单（4）</span>
        <span @click="toggletag(2)">待处理工单（4）</span>
        <span @click="toggletag(3)">待处理工单（4）</span>
      </div>
      <div class="content">
        <div class="content-wrap">
          <div class="content-item-wrap" v-for="item in tags" :key="item.title">
            <ul class="content-item">
              <li>
                <div class="content-top">
                  <span>{{ item.title }}</span>
                  <span>{{ item.righttitle }}</span>
                </div>
                <div class="content-bottom">
                  {{ item.desc }}
                </div>
              </li>
            </ul>
          </div>
        </div>
        <footer class="footer">
          清空资源代办
        </footer>
      </div>
    </section>
  </div>
</template>
<script>
export default {
  name: 'tip',
  data() {
    return {
      tags: [
        {
          title: '任务名称1',
          righttitle: '待审批',
          desc: '非王非非汪峰额分分分分额外额外份肥额外分为分为发',
        },
        {
          title: '任务名称2',
          righttitle: '待审批',
          desc: '非王非非汪峰额分分分分额外额外份肥额外分为分为发',
        },
        {
          title: '任务名称2',
          righttitle: '待审批',
          desc: '非王非非汪峰额分分分分额外额外份肥额外分为分为发',
        },
        {
          title: '任务名称2',
          righttitle: '待审批',
          desc: '非王非非汪峰额分分分分额外额外份肥额外分为分为发',
        },
        {
          title: '任务名称2',
          righttitle: '待审批',
          desc: '非王非非汪峰额分分分分额外额外份肥额外分为分为发',
        },
        {
          title: '任务名称2',
          righttitle: '待审批',
          desc: '非王非非汪峰额分分分分额外额外份肥额外分为分为发',
        },
      ],
    }
  },
  methods: {
    toggletag(tag) {
      console.log(tag)
    },
  },
}
</script>
<style lang="less" scoped>
// 弹窗
.tip-wrap {
  margin: auto;
  // height: 500px;
  width: 400px;
  background-color: #fff;
  border-radius: 3px;
  position: relative;
  color: #000;
}
.tip-header {
  border-bottom: 1px solid #ccc;
  position: relative;
}
.tip-header-title {
  color: #5897eb;
  // text-indent: 30px;
  padding-left: 30px;
  height: 50px;
  line-height: 50px;
}
.tip-header-low {
  position: absolute;
  top: 52px;
  left: 50%;
  margin-left: -40px;
  font-size: 12px;
  text-align: center;
  background-color: #fff;
  height: 16px;
  line-height: 16px;
  width: 80px;
}
.middle-tag {
  display: flex;
  justify-content: space-around;
  padding-top: 16px;
  span {
    box-sizing: border-box;
    display: inline-block;
    padding: 0 10px;
    font-size: 14px;
    // padding-bottom: 10px;
    border-bottom: 2px solid #fff;
    cursor: pointer;
    line-height: 40px;
  }
  span:hover {
    border-bottom: 2px solid #5897eb;
    color: #5897eb;
  }
}
.content {
  // position: relative;
  // height:100%;
}
.content-wrap {
  margin-bottom: 59px;
}
.content-item {
  margin: 0 30px;
  border-bottom: 1px solid #eeeeee;
}
.content-top {
  display: flex;
  justify-content: space-between;
  padding: 10px 0px;
  line-height: 20px;
}
.content-bottom {
  padding: 0px 0px 10px 0;
  font-size: 12px;
  width: 264px;
  line-height: 20px;
}
.content-item-wrap:hover {
  background: #e9f7fe;
  .content-item {
    border-bottom: 1px solid #e9f7fe;
  }
}
.footer {
  height: 60px;
  line-height: 60px;
  text-align: center;
  position: absolute;
  bottom: 0;
  width: 100%;
  border-top: 1px solid #ccc;
  margin-top: 30px;
  // left:50%;
  // margin-left: -200px;
}
</style>
