<template>
  <div class="archetypes">
    <section class="introduction">
      <p>Choice of Kung-Fu Styles</p>
    </section>
    <div class="selector-container">
      <SearchableList placeholder="Search for a style..." :items="archetypes" @select-item="selectItem" />
      <DetailedList :items="selectedList" />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import SearchableList from '@/components/SearchableList.vue'; // @ is an alias to /src
import DetailedList from '@/components/DetailedList.vue';
import {archetypes} from '@/data/archetypes.tsx';

export default Vue.extend({
  name: 'home',
  components: {
    SearchableList,
    DetailedList,
  },
  data() {
    return {archetypes};
  },
  computed: {
    selectedList: function() {
      return this.archetypes.filter(element => element.selected);
    },
  },
  methods: {
    selectItem(item) {
      this.archetypes = this.archetypes.map((element) => {
        if (element.key === item.key) {
          element.selected = !element.selected;
          element.cost = 4;
          return element;
        }
        return element;
      });
    },
  },
});
</script>

<style lang="scss" scoped>
.selector-container, .introduction {
  display: flex;
  width: 1200px;
  margin: auto;
}

.introduction p {
  padding: 0 10px;
}
</style>
