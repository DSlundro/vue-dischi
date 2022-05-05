<template>
  <footer>
    <div class="wrapper">
    <!-- facebook -->
    <div class="icon facebook" @click="fb" :class="facebook === false ? '' : 'fb'">
        <div class="tooltip">Facebook</div>
        <span><i class="fab fa-facebook-f"></i></span>
    </div>

    <!-- twitter -->
    <div class="icon twitter">
        <div class="tooltip">Twitter</div>
        <span><i class="fab fa-twitter"></i></span>
    </div>

    <!-- instagram -->
    <div class="icon instagram">
        <div class="tooltip">Instagram</div>
        <span><i class="fab fa-instagram"></i></span>
    </div>

    <!-- github -->
    <div class="icon github">
        <div class="tooltip">Github</div>
        <span><i class="fab fa-github"></i></span>
    </div>

    <!-- youtube -->
    <div class="icon youtube">
        <div class="tooltip">Youtube</div>
        <span><i class="fab fa-youtube"></i></span>
    </div>

    <!-- whatsapp -->
    <div class="icon whatsapp">
        <div class="tooltip">Whatsapp</div>
        <span><i class="fab fa-whatsapp"></i></span>
    </div>
</div>
  </footer>
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

<style>
.wrapper{
    display: flex;
    justify-content: center;
    align-content: center;
    margin-top: 50vh;
}

.wrapper .icon{
    position: relative;
    border-radius: 50%;
    padding: 5px;
    margin: 2px;
    width: 40px;
    height:40px;
    font-size: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    cursor: pointer;
}

.wrapper .icon i{
    transition: .4s linear;
}

.wrapper .icon::before,
.wrapper .icon::after{
    content: '';
    position: absolute;
    box-sizing: border-box;
    width: 100%;
    height: 100%;
    left: 0;
    top: 0;
    transition: .3s linear;
}

.wrapper .icon:hover::before{
    border-radius: 50%;
    border-left: 4px solid;
    border-right: 4px solid;
    transform: skewX(25deg);

}

.wrapper .icon:hover::after{
    border-radius: 50%;
    border-top: 4px solid;
    border-bottom: 4px solid;
    transform: skewY(-25deg);
}

.wrapper .tooltip{
    position: absolute;
    top: 0;
    font-size: 14px;
    padding: 4px 8px;
    border-radius: 4px;
    opacity: 0;
    pointer-events: none;
    transition: all .3s cubic-bezier(0.68, -0.55, 0.265, 1.555);
}

.wrapper .icon:hover .tooltip{
    top: -45px;
    opacity: 1;
    visibility: visible;
    pointer-events: auto;
}

.fb{color: #166fe5; border: #166fe5;}
.tw{color: #1a8cd8; border: #1a8cd8;}
.ig{color: #D30140; border: #D30140;}
.gh{color: #23272d; border: #23272d;}
.yt{color: #ff0000; border: #ff0000;}
.wp{color: #00e676; border: #00e676;}
</style>

