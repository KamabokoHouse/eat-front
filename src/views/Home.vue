<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
    <p>緯度: {{ longitude }}</p>
    <p>経度: {{ latitude }}</p>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src

@Component({
  components: {
    HelloWorld
  }
})
export default class Home extends Vue {
  public latitude: number = 0;
  public longitude: number = 0;

  /**
   * getCurrentPosition
   * infrastructure層に移動予定
   */
  public getCurrentPosition() {
    const options = {
      enableHighAccuracy: true,
      timeout: 5000,
      maximumAge: 0
    };

    function error(err: PositionError) {
      console.warn(`ERROR(${err.code}): ${err.message}`);
    }

    navigator.geolocation.getCurrentPosition(
      (pos: Position) => {
        const crd = pos.coords;
        this.latitude = crd.latitude;
        this.longitude = crd.longitude;
      },
      error,
      options
    );
  }
  public mounted() {
    this.getCurrentPosition();
  }
}
</script>
