<template>
  <div>
    <input :type="type" />
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class InputComponent extends Vue {
  @Prop() private type!: string;
  //Model
}
</script>
