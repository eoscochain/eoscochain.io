<template lang="pug">
.page
  page-menu
    router-link(:to="{ name: 'validators'}")  {{ $t('Overview') }}
    router-link(:to="{name: 'validator-faq'}")  {{ $t('FAQ') }}
    router-link(:to="{ name: 'testnet-tutorial'}")  {{ $t('TestnetTutorial') }}
  router-view
</template>

<script>
import PageMenu from "common/NiPageMenu"
export default {
  name: "page-validators",
  metaInfo: { title: "Validators" },
  components: {
    PageMenu
  }
}
</script>
