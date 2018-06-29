<template lang="pug">
.page
  page-menu
    router-link(:to="{ name: 'intro'}") {{ $t('Overview') }}
    router-link(:to="{ name: 'intro-hub'}") {{ $t('Pivot') }}
    router-link(:to="{ name: 'intro-further'}") {{ $t('GoingFurther') }}
  router-view
</template>

<script>
import PageMenu from "common/NiPageMenu"
export default {
  name: "page-intro",
  metaInfo: { title: "Introduction" },
  components: {
    PageMenu
  }
}
</script>
