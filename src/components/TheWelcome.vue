<script setup>
import WelcomeItem from "./WelcomeItem.vue";
import DocumentationIcon from "./icons/IconDocumentation.vue";
import ToolingIcon from "./icons/IconTooling.vue";
import EcosystemIcon from "./icons/IconEcosystem.vue";
import CommunityIcon from "./icons/IconCommunity.vue";
import SupportIcon from "./icons/IconSupport.vue";
</script>

<template>
  <WelcomeItem>
    <template #icon>
      <DocumentationIcon />
    </template>
    <template #heading>Documentation</template>

    UnitDomains javascript lib’s
    <a href="https://docs.unit.domains/dapp/" target="_blank" rel="noopener"
      >official documentation</a
    >
    provides you with all information you need to get started.
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <ToolingIcon />
    </template>
    <template #heading>Sample Code</template>
    <div>
      <pre>
      <code>
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
</code>
    </pre>
    </div>
  </WelcomeItem>
</template>
