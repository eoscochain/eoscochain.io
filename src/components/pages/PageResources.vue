<template lang="pug">
.page
  page-menu
    router-link(:to="{name: 'resources'}") {{ $t('Overview') }}
    router-link(:to="{name: 'whitepaper'}") {{ $t('Whitepaper') }}
    router-link(:to="{name: 'faq'}") {{ $t('FAQ') }}
    router-link(:to="{name: 'plan'}") {{ $t('Plan') }}
    router-link(:to="{name: 'academy'}") {{ $t('Academy') }}
    router-link(:to="{name: 'delegators'}") {{ $t('Delegators') }}
  router-view
</template>

<script>
import PageMenu from "common/NiPageMenu"
export default {
  name: "page-resources",
  metaInfo: { title: "Resources" },
  components: {
    PageMenu
  }
}
</script>
