<template>
  <div class="demo-slot">
    <h1>DemoSlot</h1>
      <comp-tabs title="Tiêu đề của Tabs">
        <ul class="tabs-header">
          <li
            v-for="(item,index) in tabsHeader"
            :key = "index"
            @click="setActiveTab(index)"
            :class="{active: tabActive == index}">
            {{ item.text }}</li>
        </ul>
        <div class="tab-content tab1" v-if="tabActive==0">
          <p>Lorem1 ipsum dolor sit amet consectetur adipisicing elit. Cumque, earum?</p>
        </div>

        <div class="tab-content tab2" v-if="tabActive==1">
          <p>Lorem2 ipsum dolor sit amet consectetur adipisicing elit. Cumque, earum?</p>
        </div>

        <div class="tab-content tab3" v-if="tabActive==2">
          <p>Lorem3 ipsum dolor sit amet consectetur adipisicing elit. Cumque, earum?</p>
        </div>
      </comp-tabs>
    <h1>DemoSlot</h1>
  </div>
</template>

<script>
import CompTabs from './CompTabs'

export default {
  name: 'demo-slot',
  components: {
    CompTabs
  },
  data() {
    return {
      tabsHeader: [
        { text: 'Tab1' },
        { text: 'Tab2' },
        { text: 'Tab3' }
      ],
      tabActive: 0
    }
  },
  methods: {
    setActiveTab(index) {
      console.log('setActiveTab', index);
      this.tabActive = index;
    }
  }
}
</script>

<style>
  .demo-slot {
    margin: 10px 0px;
    border: 1px solid #000;
  }
</style>
