<template>
  <div>
    <div class="contanier-fluid">
      <div class="m-4">
        <div class="container text-center">
          <div class="col-sm-6">
            <div class="row row-cols-auto">
              <div class="col-sm-2">
                <div class="col dot"></div>
              </div>
              <div class="col-sm-2">
                <div class="col dot2"></div>
              </div>
              <div class="col-sm-2">
                <div class="col dot3"></div>
              </div>
          </div>
    </div>
  </div>
    <div class="container text-center">
      <div class="m-4">
        <div class="row">
          <div class="col-sm-4">
              <div class="card" style="width: 18rem;">
                  <div class="card-body">
                  <div class="dot"></div>
                  </div>
                </div>
            </div>
            <div class="col-sm-4">
              <div class="card" style="width: 18rem;">
                  <div class="card-body">
                  <div class="dot2"></div>
                  </div>
                </div>
            </div>
            <div class="col-sm-4">
              <div class="card" style="width: 18rem;">
                  <div class="card-body">
                  <div class="dot3"></div>
                  </div>
                </div>
            </div>
          </div> 
        </div>
      </div>
      </div>
    </div>
  </div>
</template>
<style>
.dot {
  height: 25px;
  width: 25px;
  background-color: #ff0000;
  border-radius: 50%;
  display: inline-block;
}
.dot2 {
  height: 25px;
  width: 25px;
  background-color: #198753;
  border-radius: 50%;
  display: inline-block;
}
.dot3 {
  height: 25px;
  width: 25px;
  background-color: #0056ba;
  border-radius: 50%;
  display: inline-block;
}
.content{
  width: 5%;
  height: 40px;
  display: inline-block;
}
</style>
<script>
//import Header from '../components/Header.vue';
export default {
    name: "IndexPage",
  //  components: { Header }
  data: () => ({
        posts: []
      }),
      async fetch() {
        this.posts = await this.$http.$get('https://api.nuxtjs.dev/posts')
      },
      fetchOnServer: false,
      // multiple components can return the same `fetchKey` and Nuxt will track them both separately
      fetchKey: 'site-sidebar',
      // alternatively, for more control, a function can be passed with access to the component instance
      // It will be called in `created` and must not depend on fetched data
      fetchKey(getCounter) {
        // getCounter is a method that can be called to get the next number in a sequence
        // as part of generating a unique fetchKey.
        return this.someOtherData + getCounter('sidebar')
      }
}
</script>
