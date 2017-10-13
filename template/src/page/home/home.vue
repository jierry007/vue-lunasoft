<template>
    <div class="page-home">
      <hello></hello>
      <p>
        <a href="https://github.com/vuejs-templates" target="_blank">built yourself template , click it</a>
      </p>
    </div>
</template>

<script>
    import Hello from '../../components/HelloWorld.vue'
    export default {
        name: 'page-home',
        data() {
            return {}
        },
        filters: {},
        methods: {},
      watch: {
        /**
         * 一个监测路由的 request
         */
        '$route': function () {
          console.log(this.$route)
            this.$http.get('/api/url', {
              params: {
                id: 'params'
              }
            })
            .then( res => {
                console.log(res)
            })
            .catch( err => {
              console.log(err)
            });
        }
      },
        components: {
          Hello
        },
        mounted: function () {
        },
    }
</script>

<style lang="less">
   @import "home";
</style>
