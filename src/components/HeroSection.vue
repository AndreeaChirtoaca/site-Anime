<template>
  <div class="heroSection">
    <div class="showImage">
      <div class="heroImageFrame">
        <img class="heroImage" :src="image">
      </div>
    </div>
    <div class="showText">
      <h1 id="title">{{title}}</h1>
      <div>
        <p class="description" :class="{seeAll: see}">{{description}}</p>
        <button class="seeMore" v-if="!see" @click="seeMore">...See more</button>
      </div>
      <button class="buttonHero" @click="goToShow()">Watch</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeroSection",
  props: {
    title: String,
    subtitle: String,
    description: String,
    image: String
  },
  data: function() {
    return {
      see: false
    };
  },
  methods: {
    goToShow: function() {},
    seeMore: function() {
      this.see = true;
    }
  }
};
</script>

<style scoped>
.heroSection {
  --background-color:rgb(182, 161, 161);
  padding: 10px;
  background: var(--background-color);
  display: flex;
  align-items: start;
  
}
.showText {
  text-align: left;
  padding: 25px 20px 25px 30px;
}
.heroImage {
  margin: 0;
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  object-fit: cover;
}
.heroImageFrame {
  padding-top: 150%;
  height: 0;
  position: relative;
}
.showImage {
  margin: 0px;
  border-bottom: 2px solid black;
  padding: auto;
  flex: 0 0 200px;
  max-width: 200px;
}
.description {
  --line-height: 20px;
  --n-of-lines: 2;
  --max-height: calc(var(--line-height)*var(--n-of-lines));
  padding-left: 10px;
  margin: 5px;
  max-width: 90%;
  line-height: var(--line-height);
  max-height: var(--max-height);
  overflow: hidden;
  text-overflow: ellipsis;
}
.seeAll{
--n-of-lines: ;
}
.seeMore {
  padding-left: 10px;
  margin: 10px;
  cursor: pointer;
  color: rgb(201, 77, 32);
  font-family: Roboto;
  font-weight: bold;
  border: none;
  background: var(--background-color);
}
.seeMore:hover{
text-decoration: underline;
}

.buttonHero {
  font-family: Roboto;
  font-weight: normal;
  border: none;
  cursor: pointer;
  padding: 7px 10px;
  min-width: 130px;
  margin-left: 15px;
  margin-right: 10px;
  font-size: 16px;
  border-radius: 5px;
  background-color: rgb(235, 105, 57);
  line-height: 28px;
  color: white;
}
.buttonHero:hover {
  text-decoration: underline;
}
</style>
