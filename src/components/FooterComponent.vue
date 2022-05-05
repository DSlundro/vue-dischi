<template>
<div></div>
</template>

<script>
export default {
    name: 'SiteFooter',
    facebook: false,

    methods:{
      fb(){
        if (this.facebook === false) {
          this.facebook = true;
        }
        else{this.facebook = false}
      }
    }
}
</script>

