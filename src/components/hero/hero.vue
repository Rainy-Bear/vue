<template>
  <div class="hero">
    <div class="heroType">
      <span class="heroTypeTxt">英雄分类</span>
      <div class="heroTypeCon">
        <router-link
          class="typeList"
          v-for="(item, index) in typeListArr"
          :key="item.heroTypeId"
          :to="{name:'heroList',params:{heroTypeId: item.heroTypeId}}"
          :class="{marRight:(index + 1) % 3 !== 0,marTop:index > 2}"
        >
          <img :src="item.heroTypeImg" alt>
          <span
            :class="{bgOne: index===0,bgTwo: index===1,bgThree: index===2,bgFour: index===3,bgFive: index===4,bgSix: index===5}"
          ></span>
          <span class="heroTypeName">{{item.heroTypeName}}</span>
        </router-link>
        <div class="clear"></div>
      </div>
    </div>
    <div class="strategy">
      <span class="strategyTxt">攻略</span>
      <span class="valueBook" @click="clickValueBook">电竞专业术语宝典</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "hero",
  data() {
    return {
      typeListArr: ""
    };
  },
  mounted: function() {
    this.$nextTick(() => {
      this.$http
        .get("/api/heroType/heroType")
        .then(result => {
          this.typeListArr = result.data;
        })
        .catch(result => {
          console.log(result);
        });
    });
  },
  methods: {
    clickValueBook: function() {
      this.$router.push("/valueBook");
    }
  }
};
</script>

<style scoped>
.clear {
  clear: both;
}

.hero {
  width: 94%;
  margin: 95px auto 0 auto;
}

.hero .heroType .heroTypeTxt,
.hero .strategy .strategyTxt {
  width: 80px;
  font-size: 20px;
  font-weight: bold;
}

.hero .heroTypeCon {
  width: 100%;
  margin-top: 10px;
}

.hero .heroTypeCon .typeList {
  position: relative;
  width: 32%;
  float: left;
}

.hero .heroTypeCon .marRight {
  margin-right: 2%;
}

.hero .heroTypeCon .marTop {
  margin-top: 8px;
}

.hero .heroTypeCon .typeList img {
  display: block;
  width: 100%;
  border-radius: 8px;
  object-fit: cover;
  filter: opacity(0.7) saturate(3);
  -webkit-filter: opacity(0.7) saturate(3);
  -moz-filter: opacity(0.7) saturate(3);
  -o-filter: opacity(0.7) saturate(3);
}

.hero .heroTypeCon .typeList .bgOne,
.hero .heroTypeCon .typeList .bgTwo,
.hero .heroTypeCon .typeList .bgThree,
.hero .heroTypeCon .typeList .bgFour,
.hero .heroTypeCon .typeList .bgFive,
.hero .heroTypeCon .typeList .bgSix {
  position: absolute;
  top: 0;
  left: 0;
  border-radius: 8px;
  width: 100%;
  height: 100%;
  filter: opacity(0.7);
}

.hero .heroTypeCon .typeList .bgOne {
  background-image: linear-gradient(to top right, #1057fc, #7cfcfc);
}

.hero .heroTypeCon .typeList .bgTwo {
  background-image: linear-gradient(to top right, #ffa042, #fff0ac);
}

.hero .heroTypeCon .typeList .bgThree {
  background-image: linear-gradient(to top right, #37c84d, #ffff80);
}

.hero .heroTypeCon .typeList .bgFour {
  background-image: linear-gradient(to top right, #99dce6, #ffd5cf);
}

.hero .heroTypeCon .typeList .bgFive {
  background-image: linear-gradient(to top right, #b92fb9, #ffff80);
}

.hero .heroTypeCon .typeList .bgSix {
  background-image: linear-gradient(to top right, #ff2d2d, #79ff79);
}

.hero .heroTypeCon .typeList .heroTypeName {
  position: absolute;
  color: #ffffff;
  top: 70px;
  left: 20px;
  opacity: 1;
}

.hero .strategy {
  width: 100%;
  margin-top: 10px;
}

.hero .strategy .valueBook {
  display: block;
  width: 100%;
  height: 80px;
  color: #ffffff;
  font-size: 15px;
  letter-spacing: 1px;
  margin-top: 10px;
  text-align: center;
  line-height: 80px;
  border-radius: 8px;
  background-color: #7b64f2;
}
</style>
