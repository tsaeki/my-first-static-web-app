<template>
  <div>{{ message }} / {{message1}}</div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      message: "",
      message1: ""
    };
  },
  async mounted() {
    const { text } = await (await fetch("/api/message")).json();
    this.message = text;
    const { text1 } = await (await fetch("/api/test1")).json();
    this.message1 = text1;
  }
};
</script>