<template>
  <a-layout-header
    class="header"
    :style="{ position: 'fixed', zIndex: 5, width: '100%', backgroundColor: '#FFFFFF', borderBottom: '1px solid #e8e8e8' }"
  >
    <a href="/#/" style="color:rgba(0, 0, 0, 0.65)">
      <div class="logo">
        <img src="../assets/logo.png" />
        <p>Idea Ocean</p>
      </div>
    </a>

    <div class="searchBoxContainer">
      <a-button href="/#/mycove" :type="control.index ? 'default' : 'primary'" class="menuButton" size="large">Welcome, Cornfield Warrior</a-button>
      <a-input-search
        v-model="state.query"
        class="box searchbox menuButton"
        v-if="!control.index"
        placeholder="Search the Ocean"
        @search="onSearch"
      ></a-input-search>
    </div>
  </a-layout-header>
</template>

<script>
import store from "../store";

export default {
  data: function() {
    return {};
  },
  computed: {
    control() {
      return store.state.control;
    },
    state() {
      return store.state;
    }
  },
  mounted() {},
  methods : {
    onSearch : function() {
      this.$router.push("search");
    }
  }
};
</script>

<style scoped>
.logo {
  height: 64px;
  margin: 0px;
  float: left;
}

.logo img {
  margin: 7px 24px 7px 0;
  float: left;
  height: 50px;
}

.logo p {
  margin: 3px 24px 3px 0;
  float: left;
  height: 58px;
  font-size: 22px;
  text-align: center;
  font-family: "IdeaHeadlineBold";
}

.searchBoxContainer {
  float: right;
  width: 700px;
  height: 64px;
}

.searchbox {
  float: left;
  width: 410px;
  margin: 16px 0px 16px 8px;
  top: 0;
  bottom: 0;
}

.menuButton {
  height: 40px;
  margin: 13px 0px 13px 8px;
  float: right;
}
</style>