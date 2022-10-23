<script setup>
defineProps({
  msg: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <h3>
      Domain name resolution
      <input type="text" :value="domainName" />
      <button @click="domainResolution" type="button">Resolution</button>
    </h3>
  </div>
</template>

<script>
import { UnitDomains } from "@unitdomains/unitdomainsjs";
export default {
  setup() {},
  data() {
    return { domainName: "hello.cat" };
  },
  methods: {
    async domainResolution() {
      if (window && typeof window.ethereum !== "undefined") {
        const unitdomains = await UnitDomains.create(window.ethereum);

        console.log(await unitdomains.addr("hello.cat"));
        console.log(await unitdomains.owner("hello.cat"));
        console.log(await unitdomains.resolver("hello.cat"));
        console.log(await unitdomains.ttl("hello.cat"));
        console.log(await unitdomains.available("hello.cat"));
        console.log(await unitdomains.rentPrice("hello.cat", 1));
        console.log(await unitdomains.registerPrice("hello.cat"));
      }
    },
  },
};
</script>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
