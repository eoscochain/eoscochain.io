<template lang="pug">
.page
  page-menu
  page(:title="$t('about')" :subtitle="$t('EOS Cochain is supported by the Cochain Foundation .')")
    div(slot="menu")
      btn(icon="person_add" value="join us!" type="anchor" href="https://github.com/eoscochain" target="_blank" color="primary")
//
    part(title='Interchain Foundation')
      cards.people
        card-person(group='icf', v-for="person in ppl('icf')", :key='person.slug', :person='person')

    part(title='Tendermint Team')
      cards.people
        card-person(group='aib', v-for="person in ppl('aib')", :key='person.slug', :person='person')
</template>

<script>
import { mapGetters } from "vuex"
import Btn from "@nylira/vue-button"
import CardPerson from "cards/CardPerson"
import Cards from "common/NiCards"
import Page from "common/NiPage"
import PageMenu from "common/NiPageMenu"
import Part from "common/NiPart"
export default {
  name: "page-about",
  metaInfo: { title: "About" },
  components: {
    Btn,
    Cards,
    CardPerson,
    Page,
    PageMenu,
    Part
  },
  computed: {
    ...mapGetters(["people"])
  },
  methods: {
    ppl(tag) {
      if (this.people) {
        return this.people.filter(p => p.groups[tag])
      } else {
        return []
      }
    }
  }
}
</script>

<style lang="stylus">
@import '~variables'

.people
  margin-bottom 1rem

@media screen and (min-width: 768px)
  .people
    .ni-card-person
      flex 0 0 50%

@media screen and (min-width: 1024px)
  .people
    .ni-card-person
      flex 0 0 33.333%
</style>
