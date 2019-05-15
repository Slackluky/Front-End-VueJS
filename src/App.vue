<template>
  <div id="app">
    <div class="head">

      <img src="./assets/logo.png" />
      <p>created by Luky Setiawan</p>

    </div>
    <div class="container-fluid">
          <div class="container ">
          <div class="row">
        <div class="col-2">
          </div>
            <div class="col-8">
              <h5>The most delicious jobs for designers</h5> 
            </div>
            <div class="col-2">
          <button type="button" class="btn btn-light"><font-awesome-icon icon="search" /></button>
          </div>
          </div>
          </div>
<ul v-if="items && items.length">
  <li v-for="item of items" :key="item">
    <div class="card border-0 align-items-center">
        <div class="row " >
            <div class="col-4 align-self-center ">
              <div class="image" >
                <img v-bind:src="item.image" alt="">
                </div>
            </div>
            <div class="col-8 align-self-center">
                <div class="card-body" >
                    <p class="card-tittle"><b>{{item.job}}</b></p>
                    <h6 class="card-text">{{item.company}}</h6>
                    <h6 class="card-text2">{{item.address}}</h6>
                </div>
            </div>
        </div>
  </div>
  </li>
</ul>
      </div>
    </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'app',
  data () {
    return {
      items:[]
    }
  },
 mounted () {
    axios
      .get('https://api.myjson.com/bins/reyab')
      .then(response => (this.items = response.data.data))
  }
}
</script>
<style lang="scss" scoped>
   @import 'style.scss';
   @import '../node_modules/bootstrap/scss/bootstrap.scss';
</style>

