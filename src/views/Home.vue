<template>
  <div>
    <h1>Welcome to {{ title }}!</h1>
    <div class="container">
      <div class="row">
        <div class="card w-100 mb-2">
          <div class="card-body">
            <div class="col-12">
              <label>
                <input type="text" class="form-control" v-model="inputText" />
              </label>
            </div>
            <div class="col-12">
              <div class="btn-group">
                <button class="btn btn-primary" type="button" @click="getData">Get</button>
                <button class="btn btn-warning" type="button" @click="setData">Set</button>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="row w-100">
        <label class="w-100">
          <select class="form-control" v-model="region" @change="changeRegion">
            <option :key="i" :value="d.v" v-for="(d, i) in options">{{d.t}}</option>
          </select>
        </label>
      </div>

      <div class="row">
        <table class="table table-bordered" v-if="tableShow">
          <tr :key="i" v-for="(d, i) in options">
            <th>{{d.v}}</th>
            <td>{{d.t}}</td>
          </tr>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      title: 'this is developer',
      inputText: 'abc',
      options:[{
        v: 's', t: 'seoul',
      }, {
        v: 'l', t: 'love',
      }, {
        v: 'j', t: 'jeju',
      }],
      region: 'j',
      tableShow: true
    }
  },
  watch: {
    inputText() {
      console.log('watch');
      console.log(this.inputText);
    }
  },
  methods: {
    getData() {
      alert(this.inputText);
    },
    setData() {
      this.inputText = 'test';
    },
    changeRegion() {
      alert(this.region);
    }
  },
  beforeCreate() {
    console.log('beforeCreate');
  },
  created() {
    console.log('created');
  },
  beforeMount() {
    console.log('beforeMount');
  },
  mounted() {
    console.log('mounted');
  },
  beforeUpdate() {
    console.log('beforeUpdate');
  },
  updated() {
    console.log('updated');
  },
  beforeDestroy() {
    console.log('beforeDestroy');
  },
  destroyed() {
    console.log('destroyed');
  }
}
</script>

<style scoped>

</style>