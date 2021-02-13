<template>
  <div>
    <h1>Welcome to {{ title }}!</h1>
    <label>
      <input type="text" v-model="inputText" />
    </label>
    <button type="button" @click="getData">Get</button>
    <button type="button" @click="setData">Set</button>

    <select class="form-control" v-model="region" @change="changeRegion">
      <option :key="i" :value="d.v" v-for="(d, i) in options">{{d.t}}</option>
    </select>

    <table class="table table-bordered" v-if="tableShow">
      <tr :key="i" v-for="(d, i) in options">
        <th>{{d.v}}</th>
        <td>{{d.t}}</td>
      </tr>
    </table>
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
      tableShow: false
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