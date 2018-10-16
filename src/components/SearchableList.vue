<template>
  <aside>
    <div class="searchbox">
      <input type="search" :placeholder="placeholder" v-model="filter" />
    </div>
    <div class="results">
      <div v-for="item in filteredList" v-bind:key="item.key" :class="{selected: item.selected}" @click="$emit('select-item', item)">
        <span>{{ item.name }}</span>
        <span v-if="item.selected" class="result-cost">{{ item.cost }}</span>
      </div>
    </div>
  </aside>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'SearchableList',
  props: {
    items: Array,
    placeholder: String,
  },
  data() {
    return {filter: ''};
  },
  computed: {
    filteredList() {
      if (this.filter === '') { return this.items; }
      return this.items.filter((item) => {
        return item.name.toLowerCase().indexOf(this.filter.toLowerCase()) !== -1;
      });
    },
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
aside {
  border: 1px solid black;
  position: relative;
  width: 300px;
  height: fit-content;
  margin: 0 10px;

  .searchbox {
    height: 40px;

    input {
      width: 100%;
      height: 100%;
      padding: 0 5px;
      font-size: 16px;
    }
  }

  .results {
    width: 300px;

    .selected {
      font-weight: 800;

      .result-cost {
        -webkit-border-radius: 15px;
        -moz-border-radius: 15px;
        border-radius: 15px;
        border: 1px solid black;
        width: 10px;
        vertical-align: middle;
        padding: 5px 10px;
      }
    }

    div {
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 40px;
      border-top: 1px solid black;
      padding: 0 10px 0 10px;
    }
  }
}
</style>
