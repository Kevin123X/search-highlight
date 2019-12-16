<template>
  <div class="search">
    <p v-html="searchContent"></p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    search_key: {
      type: String,
      default: ""
    },
    content: {
      type: String,
      default: ""
    }
  },
  computed: {
    searchContent() {
      if (this.search_key) {
        let search_key = this.search_key;
        let search_content = this.content;
        let highLightStr = search_content.replace(
          search_key,
          `<span style="color:red">${search_key}</span>`
        );
        return highLightStr;
      } else {
        return this.content
      }
    }
  },
  mounted() {},
  methods: {
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>
h1,
h2 {
  font-weight: normal;
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
.search {
  width: 1200px;
  margin: 50px auto;
  .operate {
    margin-bottom: 50px;
    display: flex;
    flex-wrap: nowrap;
    align-items: center;
    justify-content: center;
    input {
      width: 300px;
      height: 36px;
      border: 1px solid #dddddd;
      font-size: 14px;
      color: #666666;
      padding: 10px;
      outline: none;
      line-height: 36px;
      &::placeholder {
        font-size: 14px;
        line-height: 36px;
        color: #999999;
      }
    }
    button {
      width: 80px;
      height: 36px;
      border: 1px solid #dddddd;
      border-left: none;
      line-height: 36px;
      text-align: center;
      font-size: 14px;
      color: #666666;
      outline: none;
      cursor: pointer;
    }
  }
  p {
    width: 800px;
    white-space: pre-wrap;
    word-break: break-all;
    font-size: 14px;
    color: #aaaaaa;
    margin: 0 auto;
    text-indent: 2em;
    text-align: left;
    line-height: 1.6;
  }
}
</style>
