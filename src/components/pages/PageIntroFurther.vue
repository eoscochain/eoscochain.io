<template lang="pug">
page(:title="$t('GoingFurther')" :subtitle="$t('Wish to learn more?')")
  div(slot="menu"): btn(icon="chat" :value="$t('CommunityChat')" type="anchor" href="https://t.me/EOSCochainProject" target="_blank" color="primary")
  part(:title="$t('More Resources')")
    list-item(:to="{ name: 'whitepaper' }" :title="$t('Read the EOS Cochain whitepaper')" icon="description")
    list-item(:to="{ name: 'faq' }" :title="$t('Read the EOS Cochain FAQ')" icon="description")
    list-item(:to="{ name: 'testnet' }" :title="$t('Participate in the testnet')" icon="description")
    list-item(:to="{ name: 'developers' }" :title="$t('Learn how to develop on EOS Cochain')" icon="description")
</template>

<script>
import Btn from "@nylira/vue-button"
import ListItem from "common/NiListItem"
import Page from "common/NiPage"
import Part from "common/NiPart"
export default {
  name: "page-intro-further",
  metaInfo: { title: "Going Further - Intro" },
  components: {
    Btn,
    ListItem,
    Page,
    Part
  }
}
</script>
