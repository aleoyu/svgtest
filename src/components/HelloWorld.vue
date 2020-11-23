<template>
  <div class="hello">
    注：发现只要不是虚拟dom的都正常显示及点击。
    <h3>1、v-html生成显示正常也可点击:</h3>
    <div v-html="svgdata"></div>
    <br /><h3>2、render 生成显示的高度不对并且点击后动画无效：</h3>
    <article-content :html="svgdata" />
    <br /><h3>3、template直接生成显示:</h3>
    <div><section data-width="100%" style="display: inline-block; width: 100%; font-size: 0px; background-image: url(&quot;https://pic.nfapp.southcn.com/nfplus/ossfs/pic/xy/202010/27/4d8553b6-a2f1-4513-94f4-d44cdbece87e.jpg&quot;); background-position: 0% 0%; background-size: cover; vertical-align: top; background-repeat: no-repeat; background-attachment: scroll; box-sizing: border-box; text-align: center; max-width: 100% !important;"><svg data-width="100%" enable-background="new 0 0 750 929" space="preserve" version="1.1" viewbox="0 0 750 929" x="0px" xlink="http://www.w3.org/1999/xlink" xml="" xmlns="http://www.w3.org/2000/svg" y="0px" style="display: inline-block; outline: none; opacity: 0; width: 100%; margin-top: -1px; border-width: initial; border-style: none; border-color: initial; vertical-align: top; background-position: 0% 0%; background-repeat: no-repeat; background-size: 100%; background-attachment: scroll; background-image: url(&quot;https://pic.nfapp.southcn.com/nfplus/ossfs/pic/xy/202010/27/169399f8-d0a4-4199-baf7-c957bb65eb4e.jpg&quot;); -webkit-tap-highlight-color: transparent;"><animate attributename="opacity" from="0" to="1" begin="click" dur="1s" fill="freeze" restart="never"></animate></svg></section></div>
  </div>
</template>

<script>
import Vue from 'vue';
export default {
  name: 'HelloWorld',
  data () {
    return {
      svgdata: '<section data-width="100%" style="display: inline-block; width: 100%; font-size: 0px; background-image: url(&quot;https://pic.nfapp.southcn.com/nfplus/ossfs/pic/xy/202010/27/4d8553b6-a2f1-4513-94f4-d44cdbece87e.jpg&quot;); background-position: 0% 0%; background-size: cover; vertical-align: top; background-repeat: no-repeat; background-attachment: scroll; box-sizing: border-box; text-align: center; max-width: 100% !important;"><svg data-width="100%" enable-background="new 0 0 750 929" space="preserve" version="1.1" viewbox="0 0 750 929" x="0px" xlink="http://www.w3.org/1999/xlink" xml="" xmlns="http://www.w3.org/2000/svg" y="0px" style="display: inline-block; outline: none; opacity: 0; width: 100%; margin-top: -1px; border-width: initial; border-style: none; border-color: initial; vertical-align: top; background-position: 0% 0%; background-repeat: no-repeat; background-size: 100%; background-attachment: scroll; background-image: url(&quot;https://pic.nfapp.southcn.com/nfplus/ossfs/pic/xy/202010/27/169399f8-d0a4-4199-baf7-c957bb65eb4e.jpg&quot;); -webkit-tap-highlight-color: transparent;"><animate attributename="opacity" from="0" to="1" begin="click" dur="1s" fill="freeze" restart="never"></animate></svg></section>'
    }
  },
  components: {
    articleContent: {
      props: {
        html: String
      },
      render (h) {
        const com = Vue.extend({
          template: `<div>${this.html}</div>`
        });
        return h(com, {});
      }
    }
  },
  props: {
    msg: String
  }
}
</script>
