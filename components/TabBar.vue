<template>
  <div class="nx-tabbar">
    <div v-for="(item, index) in tabList" :key="index" :class="{'nx-tabbar-item_on': item.value == tabValue}" class="nx-tabbar-item" @click="tabClick(item.value)">{{item.label}}</div>
  </div>
</template>

<script>
import Vue from 'vue';
export default {
  data() {
    return {
      tabValue: 0,
      tabList: [
        {
          label: 'Home',
          value: 0,
        },
        {
          label: 'Info',
          value: 1,
        },
        {
          label: 'Cart',
          value: 2,
        },
        {
          label: 'User',
          value: 3,
        }
      ],
    }
  },
  methods: {
    tabClick(tabValue) {
      if(this.tabValue == tabValue) return;
      this.$emit('tabChange', tabValue, this.tabValue);
      this.tabValue = tabValue;
    }
  }
}
</script>
   
<style lang="scss">
.nx-tabbar {
    display: -webkit-box;
    display: -webkit-flex;
    display: flex;
    flex-direction: row;

  .nx-tabbar-item {
    display: block;
    -webkit-box-flex: 1;
    -webkit-flex: 1;
    flex: 1;
    flex-grow: 1;
    flex-basis: 0%;
    border-right: 1px solid white;
    word-break: break-all;
  }

  .nx-tabbar-item_on {
    transform: scaleY(1.2);
    background: #80B3FF;
    transition: all .3s ease-in-out;
    font-size: 16px;
    font-weight: bold;
    
  }
}
</style>
