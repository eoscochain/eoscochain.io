<template lang="pug">
.page
  page-menu
    router-link(:to="{ name: 'developers'}") {{ $t('Overview') }}
    router-link(:to="{ name: 'scaling-eos'}") {{ $t('ScalingEOS') }}
    // router-link(:to="{ name: 'wallet'}")  {{ $t('WalletDevelopment') }}
    // router-link(:to="{ name: 'hackatom'}") HackAtom
  router-view
</template>

<script>
import PageMenu from "common/NiPageMenu"
export default {
  name: "page-developers",
  metaInfo: { title: "Developers" },
  components: {
    PageMenu
  }
}
</script>
