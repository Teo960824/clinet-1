<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-primary sticky-top">
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item active" v-on:click='localData()' id="block-local-data">
          <a class="nav-link text-light" href="#"> 本地病案数据 <span class="sr-only">(current)</span></a>
        </li>
        <li class="nav-item active" v-on:click='serverData()' id="block-server-data">
          <a class="nav-link text-light" href="#"> 服务器病案数据 <span class="sr-only">(current)</span></a>
        </li>
        <li class="nav-item active" v-on:click='checkData()' id="block-check-data">
          <a class="nav-link text-light" href="#"> 校验数据 <span class="sr-only">(current)</span></a>
        </li>
        <li class="nav-item active" v-on:click='compDrg()' id="block-comp-drg">
          <a class="nav-link text-light" href="#"> 调用Drg分组服务 <span class="sr-only">(current)</span></a>
        </li>
        <li class="nav-item active" v-on:click='drgResult()' id="block-drg-result">
          <a class="nav-link text-light" href="#"> 停止Drg分组服务 <span class="sr-only">(current)</span></a>
        </li>
        <li class="nav-item active" v-on:click='drgRule()' id="block-drg-rule">
          <a class="nav-link text-light" href="#"> 查看Drg分组规则 <span class="sr-only">(current)</span></a>
        </li>
      </ul>
      <form class="form-inline my-2 my-lg-0" v-on:submit.prevent>
        <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search" id="block-drg-search">
      </form>
    </div>
  </nav>
</template>

<script>
  export default {
    methods: {
      localData: function () {
        this.$store.commit('BLOCK_SET_TOOLBAR', 'localData');
        this.$store.commit('SET_NOTICE', '本地病案数据');
      },
      serverData: function () {
        this.$store.commit('BLOCK_SET_TOOLBAR', 'serverData');
        this.$store.commit('SET_NOTICE', '服务器病案数据');
      },
      checkData: function () {
        this.$store.commit('BLOCK_SET_TOOLBAR', 'checkData');
        this.$store.commit('SET_NOTICE', '校验数据');
      },
      compDrg: function () {
        this.$store.commit('BLOCK_SET_TOOLBAR', 'compDrg');
        this.$store.commit('SET_NOTICE', '调用Drg分组服务');
      },
      drgResult: function () {
        this.$store.commit('BLOCK_SET_TOOLBAR', 'drgResult');
        this.$store.commit('SET_NOTICE', '停止Drg分组服务');
      },
      drgRule: function () {
        this.$store.commit('BLOCK_SET_TOOLBAR', 'drgRule');
        this.$store.commit('SET_NOTICE', '查看Drg分组规则');
      },
    },
  };
</script>

<style scoped>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  #navbarSupportedContent {
    background-image: linear-gradient(to right , #4772fe, #7997fa);
  }
  .nav-link {
    color:#ffffff;
  }

</style>
