<template>
  <div>
    <ul class="menu-wrap">
      <li
        class="menu-item"
        v-for="item in menulist"
        :key="item.title"
        @click.stop="handleclick(item.title)"
      >
        <div class="menu-item-left">
          <span>{{ item.title }}</span>
          <span>></span>
        </div>
        <ul class="inner-menu-wrap">
          <li
            class="menu-item"
            v-for="inneritem in item.children"
            :key="inneritem.title"
            @click.stop="handleclick(inneritem.title)"
          >
            <div class="menu-item-left">
              <span>{{ inneritem.title }}</span>
              <span>></span>
            </div>
            <ul class="inner-menu-wrap">
              <li
                class="menu-item"
                v-for="lowitem in inneritem.children"
                :key="lowitem.title"
                @click.stop="handleclick(lowitem.title)"
              >
                <div class="menu-item-left">
                  <span>{{ lowitem.title }}</span>
                  <span>></span>
                </div>
                <ul class="inner-menu-wrap">
                  <li
                    class="menu-item"
                    v-for="lowitem in lowitem.children"
                    :key="lowitem.title"
                    @click.stop="handleclick(lowitem.title)"
                  >
                    <div class="menu-item-left">
                      <span>{{ lowitem.title }}</span>
                      <span>></span>
                    </div>
                  </li>
                </ul>
              </li>
            </ul>
          </li>
        </ul>
      </li>
    </ul>
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
        <footer class="footer">
          清空资源代办
        </footer>
        </div>
      </section>
    </div>
  </div>
</template>
<script>
export default {
  name: 'menuright',
  data() {
    return {
      menulist: [
        {
          title: 1,
          children: [
            {
              title: 1,
            },
          ],
        },
        {
          title: 2,
          children: [
            {
              title: 2,
              children: [
                {
                  title: 2,
                },
              ],
            },
          ],
        },
        {
          title: 31,
          children: [
            {
              title: 32,
              children: [
                {
                  title: 33,
                  children: [
                    {
                      title: 34,
                    },
                  ],
                },
              ],
            },
          ],
        },
      ],
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
      ],
    }
  },
  methods: {
    handleclick(type) {
      console.log(type)
    },
    toggletag(tag){
      console.log(tag)
    }
  },
}
</script>
<style scoped lang="less">
// 菜单
.menu-item {
  position: relative;
}
.menu-wrap li {
  width: 200px;
  height: 30px;
  line-height: 30px;
  padding: 0 20px;
  background-color: #ccc;
}
.menu-item:hover {
  & > .inner-menu-wrap {
    display: block;
  }
}
.menu-wrap li:hover {
  background-color: aqua;
}
.inner-menu-wrap {
  position: absolute;
  left: 240px;
  top: 0;
  display: none;
}
.menu-item-left {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
// 弹窗
.tip-wrap {
  margin: auto;
  height: 500px;
  width: 400px;
  background-color: aquamarine;
  border-radius: 2%;
  position: relative;
}
.tip-header {
  border-bottom: 1px solid #ccc;
  position: relative;
}
.tip-header-title {
  // text-indent: 30px;
  padding-left: 30px;
  height: 50px;
  line-height: 50px;
}
.tip-header-low {
  position: absolute;
  top: 40px;
  left: 50%;
  margin-left: -40px;
  font-size: 12px;
  text-align: center;
  background-color: aquamarine;
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
    padding-bottom: 10px;
    border-bottom: 2px solid aquamarine;
    cursor: pointer;
  }
  span:hover {
    border-bottom: 2px solid blueviolet;
    color:blue;
  }
}
.content{
  // position: relative;
  // height:100%;
}
.content-item {
  margin: 0 30px;
  border-bottom: 1px solid salmon;
}
.content-top {
  display: flex;
  justify-content: space-between;
  padding: 10px 0px;
}
.content-bottom {
  padding: 0px 0px 10px 0;
  font-size: 12px;
  width: 264px;
}
.content-item-wrap:hover {
  background: skyblue;
  .content-item {
    border-bottom: 1px solid skyblue;
  }
}
.footer{
  height:60px;
  line-height: 60px;
  text-align: center;
  position: absolute;
  bottom:0;
  width:100%;
  border-top:1px solid #ccc;
  // left:50%;
  // margin-left: -200px;
}
</style>
