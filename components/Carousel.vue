<template>
  <div>
      <el-carousel :interval="4000" type="card" height="200px">
        <el-carousel-item v-for="(item, index) in recommendData" :key="index">
          <div class="article-list" :style="{backgroundImage: 'url(' + item.banner +')'}" @click="toDetail(item.link)">
            <h3>{{item.title}}</h3>
          </div>
          
        </el-carousel-item>
      </el-carousel>
  </div>
</template>

<script>
export default {
  data() {
    return {

    }
  },
  props: {
    recommendData: {
      type: Array,
      required: true
    }
  },
  methods: {
    toDetail (payload) {
      this.$router.push(payload)
    }
  },
  components: {

  }
}
</script>

<style scoped>
  .el-carousel__item h3 {
    color: #ffffff;
    font-size: 24px;
    line-height: 200px;
    margin: 0;
  }
  .article-list {
    background: no-repeat center;
    background-size: cover;
  }
</style>
