<template>
  <div class="otc">
    <legend-trade
        mode="sandbox"
        :signature="signature"
        :timestamp="timestamp"
        :app-id="appId"
        :app-key="appKey"
        :app-url="appUrl"
        app-email="kevin@ever.vision"
    ></legend-trade>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'OTC',
  props: {
    msg: String
  },
  data() {
    return {
      timestamp: "",
      signature: "",
      appId: "",
      appKey: "",
      appUrl: "",
    };
  },
  mounted() {
    this.updateInfo()
    // let script = document.createElement('script');
    // script.type = 'text/javascript';
    // script.src = 'https://www.legendtrading.com/jssdk-v3/legend-trade-full.min.js';
    // document.body.appendChild(script);

  },

  methods:{
    async updateInfo(){
      let baseURL = "https://otc-dev.everpay.io";
      const res = await axios.get(baseURL+`/auth-info`);
      console.log(res)
      this.timestamp = res.data.timestamp
      this.signature = res.data.signature
      this.appId = res.data.appId
      this.appKey = res.data.appKey
      this.appUrl = res.data.appUrl
    },
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
</style>
