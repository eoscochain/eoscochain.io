<template lang="pug">
page(:title="$t('Resources')" :subtitle="$t('A curated list of resources about the EOS Cochain.')")
  div(slot="menu"): btn(icon="chat" :value="$t('CommunityChat')" type="anchor" href="https://t.me/EOSCochainProject" target="_blank" color="primary")
  part(title="EOS Cochain")
    list-item(:to="{ name: 'whitepaper' }" :title="'EOS Cochain' + $t('Whitepaper')" icon="description")
    list-item(:to="{ name: 'faq' }" :title="'EOS Cochain' + $t('FAQ')" icon="description")
    // list-item(:to="{ name: 'plan' }" :title="'EOS Cochain' + $t('Fundraiser') + $t('Plan')" icon="description")
    // list-item(:to="{ name: 'academy' }" :title="'EOS Cochain' + $t('Academy')" icon="school")
    // list-item(:to="{ name: 'assets' }" :title="'EOS Cochain' + $t('VisualAssets')" icon="wallpaper")
    list-item(:to="{ name: 'validator-faq' }" :title="$t('ValidatorFAQ')" icon="description")
  // part(title="Cosmos Hub")
    // list-item(:to="{ name: 'delegators' }" :title="$t('DelegatorGuide')" icon="description")
    // list-item(href="https://github.com/cosmos/cosmos/raw/master/Cosmos_Token_Model.pdf" title="Cosmos Token Model (PDF)" icon="cloud_download")
  // part(title="Unofficial Resources")
       list-item(href="https://medium.com/@JesseLivermore/basic-notable-cosmos-resources-aff336febe15" title="Basic Notable Cosmos Resources" icon="link" target="_blank")
</template>

<script>
import Btn from "@nylira/vue-button"
import ListItem from "common/NiListItem"
import Part from "common/NiPart"
import Page from "common/NiPage"
export default {
  name: "page-resources-index",
  metaInfo: { title: "Resources" },
  components: {
    Btn,
    ListItem,
    Page,
    Part
  }
}
</script>
