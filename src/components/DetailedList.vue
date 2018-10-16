<template>
  <section class="detailed-list">
    <div class="detailed-item" v-for="item in items">
      <div class="text-column">
        <div class="detailed-item__header">
          <h2>{{ item.name }}</h2>
          <div>{{ item.breath }}</div>
        </div>
        <p>{{ item.description }}</p>
      </div>
    </div>
    <div class="detailed-item">
      <div class="text-column">
        <div class="detailed-item__header">
          <h2>Blossom Harvest</h2>
          <div>Cost: 4</div>
        </div>
        <div class="detailed-item__weapons">
          <span>Weapons :</span>
          <ul>
            <li>Massive</li>
            <li>Staff</li>
            <li>Unarmed</li>
          </ul>
        </div>
        <p><b>Laughts: </b> A chain is only as strong as its weakest link, and so Blossom Harvest laughs at styles that are overly complicated or full of flourishes. These intricate methods are easily smashed aside and broken. It likewise laughs at such trivialities as being outnumbered, or disadvantageous terrain – pure grit and hellish training have rendered Blossoming Heroes fearless to such things!</p>
        <p><b>Fears: </b> This style has problems when facing fighters who are reactive. Blossom Harvest’s openness is easy to read and predict, giving such opponents everything they need. It’s also ill-prepared for enemies who wield supernatural forces or influence.</p>
      </div>
      <div class="data-column">
        <h2>coin</h2>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'DetailedList',
  props: {
    items: Array,
  },
});
</script>

<style lang="scss" scoped>
.detailed-list {
  width: 855px;
  margin: 0 10px;
}

.detailed-item {
    border: 1px solid black;
    margin-bottom: 30px;
    display: flex;

    .text-column {
      width: 700px;
    }

    .data-column {
      width: 150px;
    }

    p {
      margin: 10px;
    }
}

.detailed-item__header {
  display: flex;
  justify-content: space-between;
  align-items: center;

  h2 {
    margin: 10px;
  }

  div {
    margin-right: 20px;
  }
}

.detailed-item__weapons {
  display: flex;
  align-items: center;
  padding-left: 10px;

  span {
    font-weight: 800;
  }

  ul {
    list-style-type: none;
    display: flex;
    margin: 0;
    padding-left: 10px;

    li {
      margin-right: 10px;
      padding: 5px;
      border: 1px solid black;
      -webkit-border-radius: 5px;
      -moz-border-radius: 5px;
      border-radius: 5px;
    }
  }
}
</style>
