<template lang="pug">
.page-index
  section-cover
  // section-events
  section-what
  div(style="width: 100%; text-align: center; margin-top: 5rem;")
    img(src="~images/roadmap/roadmap.png" style="max-width: 100%; max-height: 100%; text-align: center;")
  section-benefits
  // section-blog
</template>

<script>
import SectionBlog from "sections/SectionBlog"
import SectionCover from "sections/SectionCover"
import SectionEvents from "sections/SectionEvents"
import SectionWhat from "sections/SectionWhat"
import SectionBenefits from "sections/SectionBenefits"
export default {
  name: "page-index",
  metaInfo: { title: "EOS Cochain - Parachain of EOS Mainnet" },
  components: {
    SectionBlog,
    SectionCover,
    SectionEvents,
    SectionWhat,
    SectionBenefits
  }
}
</script>
