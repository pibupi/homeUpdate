<template>
  <div>
    <header class="home-header">
      <section class="header-left">
        <div class="header-menu">
          <span class="menu1"
            ><Icon type="md-menu" /> 菜单
            <side-menu class="side-menu" />
          </span>
          <span class="menu2" @mouseenter="topsshow" @mouseleave="topsshowlea"
            >Tops平台
          </span>
          <!-- <span class="menu2">Tops平台 </span> -->
        </div>
        <div class="header-tag">
          <span>我的资源</span>
          <span>+ 添加快捷菜单</span>
        </div>
      </section>
      <section class="header-right">
        <div class="msg">
          <Icon size="20" type="md-desktop" />
          <span class="badge">6</span>
          <tip class="tip" />
        </div>
        <div class="home-page"><Icon size="24" type="ios-home" /></div>
        <div class="profile"><Avatar icon="ios-person" /> jim</div>
      </section>
      <!-- <tops :class="[isshow ? 'topsblock' : 'tops']" /> -->
      <tops
        :class="[isshow ? 'topsblock' : 'tops']"
        @mouseenter="topsshow"
        @mouseleave="topsshowlea"
      />
    </header>
  </div>
</template>

<script>
import sideMenu from '../menu'
import tip from '../tip/tip'
import tops from '../tops/tops'
export default {
  name: '',
  data() {
    return {
      isshow: false,
    }
  },
  components: {
    sideMenu,
    tip,
    tops,
  },
  methods: {
    topsshow() {
      this.isshow = true
    },
    topsshowlea() {
      this.isshow = false
    },
  },
}
</script>
<style scoped lang="less">
.home-header {
  height: 60px;
  background: #041527;
  color: #fff;
  line-height: 60px;
  position: relative;
  /* display: flex; */
  /* align-items: center; */
  /* justify-content: space-between; */
}
.header-left {
  float: left;
  display: flex;
  flex: 1 1 50%;
  justify-content: space-between;
}
.header-menu {
  margin-left: 20px;
  /* flex: 1 1 60%; */
}
.menu1,
.menu2 {
  font-size: 16px;
  width: 110px;
  display: inline-block;
  margin-right: 20px;
  text-align: center;
}
.menu2 {
  transition: all 1s linear;
}
// .home-header .menu2:hover {
//   .tops {
//     display: flex;
//   }
// }
.menu1 {
  position: relative;
  &:hover {
    .side-menu {
      display: block;
    }
  }
}
// .menu1:hover
.menu1:after {
  content: '';
  display: inline-block;
  width: 2px;
  height: 16px;
  background: #fff;
  position: absolute;
  right: 0;
  top: 22px;
}
.header-tag {
  /* flex: 1 1 40%; */
  margin-left: 74px;
}
.header-tag span {
  margin-right: 20px;
  display: inline-block;
}
.header-right {
  float: right;
  display: flex;
  justify-content: space-around;
  margin-right: 20px;
  /* flex: 1 1 50%; */
  /* display: flex; */
  /* justify-items: right; */
  /* justify-content: right; */
}
.header-right div {
  margin: 0 20px 0 20px;
}
.profile {
  position: relative;
}
.msg {
  position: relative;
  &:hover {
    .tip {
      display: block;
    }
  }
}
.badge {
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background: #f50;
  position: absolute;
  top: 11px;
  right: -9px;
  color: #fff;
  line-height: 16px;
  text-align: center;
}
/* .avatar-badge {
  position: absolute;
  right: 0px;
  top: 5px;
  height: 10px;
  width: 10px;
} */
/* .ivu-badge {
  position: absolute;
  top: 20px;
} */
.side-menu {
  position: absolute;
  top: 60px;
  left: -20px;
  display: none;
}
.tip {
  position: absolute;
  top: 50px;
  left: -390px;
  display: none;
}
.tops {
  position: absolute;
  top: 60px;
  display: none;
  // transition: all 2s linear;
}
.topsblock {
  position: absolute;
  top: 60px;
  // visibility: hidden;
  display: flex;
  // transition: all 2s linear;
}
</style>
