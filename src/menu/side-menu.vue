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
  </div>
</template>

<script>
export default {
  name: 'side-menu',
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
    toggletag(tag) {
      console.log(tag)
    },
  },
}
</script>
<style scoped lang="less">
// 菜单
.menu-item {
  background-color: #041527;
  position: relative;
  // height: 30px;
}
.menu-wrap li {
  width: 260px;
  height: 50px;
  line-height: 50px;
  // padding: 0 20px;
  // background-color: #ccc;
}
.menu-item:hover {
  & > .inner-menu-wrap {
    display: block;
  }
}
.menu-wrap li:hover {
  background-color: #020b16;
}
.inner-menu-wrap {
  position: absolute;
  left: 260px;
  top: 0;
  display: none;
}
.menu-item-left {
  padding: 0 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
