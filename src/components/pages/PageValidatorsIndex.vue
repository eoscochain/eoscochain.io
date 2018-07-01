<template lang="pug">
page(
  :title="$t('Validators')"
  :subtitle="$t('Some introduction about Validators.')")
  div(slot="menu")
    btn(icon="chat" :value="$t('ValidatorChat')" type="anchor" href="https://t.me/EOSCochainProject" target="_blank" color="primary")
    btn(icon="chat" :value="$t('ValidatorForum')" type="anchor" href="https://t.me/EOSCochainProject" target="_blank")
  text-container(
    url='validators-index.md')
  text-container
    h4 {{ $t('Next') }}&hellip;
    btn(:value="$t('ValidatorFAQ')" type="link" :to="{ name: 'validator-faq' }" icon="chevron_right" icon-pos="right" color="primary" size="lg")
</template>

<script>
import Btn from "@nylira/vue-button"
import Page from "common/NiPage"
import TextContainer from "common/NiTextContainer"
export default {
  name: "page-validators-index",
  metaInfo: { title: "Overview - Validators" },
  components: {
    Btn,
    Page,
    TextContainer
  }
}
</script>
