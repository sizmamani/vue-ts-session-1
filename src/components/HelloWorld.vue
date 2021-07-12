<template>
  <div class="hello">
    //View
    <h1>{{ msg }}</h1>
    First Name: <input v-model="firstName" type="text" />
    <br />
    Last Name: <input v-model="lastName" type="text" />
    <br />
    <button @click="getPersonalInformation()" type="button">Click me</button>
    <br />
    <InputComponent :type="type" />
    <br />
    <button @click="setType('text')" type="button">Set type as Text</button>
    <button @click="setType('number')" type="button">Set type as Number</button>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
import InputComponent from "./Input.vue";
@Component({
  components: {
    InputComponent,
  },
})
export default class HelloWorld extends Vue {
  @Prop() private msg!: string;
  //Model
  firstName = "John";
  lastName = "Doe";
  type = "text";
  getPersonalInformation(): void {
    console.log(this.firstName + " " + this.lastName);
  }
  setType(type: string): void {
    this.type = type;
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
