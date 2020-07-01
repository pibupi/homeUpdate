<template>
  <div class="hello">
    <template>
      <Submenu :name="`${parentName}`">
        <template slot="title">
          <common-icon :type="parentItem.icon || ''" />
          <span>{{ showTitle(parentItem) }}</span>
        </template>
        <template v-for="item in children">
          <template v-if="item.children && item.children.length === 1">
            <side-menu-item
              v-if="showChildren(item)"
              :key="`menu-${item.name}`"
              :parent-item="item"
            ></side-menu-item>
            <menu-item
              v-else
              :name="getNameOrHref(item, true)"
              :key="`menu-${item.children[0].name}`"
              ><common-icon :type="item.children[0].icon || ''" /><span>{{
                showTitle(item.children[0])
              }}</span></menu-item
            >
          </template>
          <template v-else>
            <side-menu-item
              v-if="showChildren(item)"
              :key="`menu-${item.name}`"
              :parent-item="item"
            ></side-menu-item>
            <menu-item
              v-else
              :name="getNameOrHref(item)"
              :key="`menu-${item.name}`"
              ><common-icon :type="item.icon || ''" /><span>{{
                showTitle(item)
              }}</span></menu-item
            >
          </template>
        </template>
      </Submenu>
    </template>
    <script>
      import mixin from './mixin'
      import itemMixin from './item-mixin'
      export default {
        name: 'SideMenuItem',
        mixins: [mixin, itemMixin],
      }
    </script>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
