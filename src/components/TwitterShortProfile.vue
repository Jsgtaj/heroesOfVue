<script>
export default {
  name: "twitter-short-profile", 
  props: {
    thishero: Object
  },
  methods:{
    isFollowing(h){
      this.$set(h, "isFollowing", !h.isFollowing)
      if(h.isFollowing){
        console.log("following");
      }
      else{
        console.log("unfollowed");
      }
    }
  }
}
</script>
<template>
  <article class="dt w-100 bb b--black-05 pb2 mt2" href="#0">
    <div class="dtc w2 w3-ns v-mid">
      <img :src="thishero.pic" class="ba b--black-10 db br-100 w2 w3-ns h2 h3-ns"/>
    </div>
    <div class="dtc v-mid pl3">
      <h1 class="f6 f5-ns fw6 lh-title black mv0">{{ thishero.name }}</h1>
      <h2 class="f6 fw4 mt0 mb0 black-60">{{ thishero.twitter }}</h2>
    </div>
    <div class="dtc v-mid">
      <form class="w-100 tr" @click.prevent="isFollowing(thishero)">
        <button class="f6 button-reset bg-white ba b--black-10 dim pointer pv1 black-60" type="submit">
          {{ thishero.isFollowing === true ? "Following" : thishero.isFollowing === false ? "Unfollowed" : "Not Following" }}
        </button>
      </form>
    </div>
  </article>
</template>