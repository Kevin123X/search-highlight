<template>
  <div class="search">
    <div class="operate">
      <input
        type="search"
        v-model="search_key"
        name="search"
        id="search"
        placeholder="输入关键词搜索..."
        @input="handleChange()"
        @keydown.enter="handleSearch"
      />
      <button @click="handleSearch" :style="search_key?'background:#42b983;color:#f8f8f8':''">搜索</button>
    </div>
    <Search-Content :search_key="confirmSearch" :content="initContent"></Search-Content>
  </div>
</template>

<script>
import SearchContent from "./SearchContent";
export default {
  name: "SearchHighLight",
  components: { SearchContent },
  data() {
    return {
      search_key: "",
      confirmSearch: "",
      initContent: `来路不知走了多长，但我知道，我念你，足够同我走到天涯海角，季节不知更迭了多少春秋，但我知道，每一季的花开花落，都有我无声的为你歌唱，灯火不知照亮了多少梦，但我知道，万家通明中总有一盏是为你守候。如果，江海河流翻涌的潮汐，是你的思念，那么，我能否是水岸边等待潮汐靠近的一颗石头，如果，朝阳暮霞锦绣的山林草木，是你眼中的风景，那么，我能否是缱绻在山林草木上的一缕风烟，如果，雨露霜雪点触的屋檐瓦砾，是你心灵的归处，那么，我能否是屋檐瓦砾中的一扇门窗。`
    };
  },
  mounted() {},
  methods: {
    handleChange() {
      if (!this.search_key) {
        this.confirmSearch = this.search_key;
      }
    },
    handleSearch(type) {
      this.confirmSearch = this.search_key;
    }
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
