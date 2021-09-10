<template>
  <section id="what-i-do" class="container content-title WhatIdo-page">
    <Card v-for="(data, index) in WhatIDo" :key="index" :Image="data.Image" :Title="data.Title" :Description="data.Description"/>
  </section>
</template>

<script>
import Card from "./UI/Card"
import { WhatIDo } from "/Data.json"

export default {
  components: { Card },
  data(){
    return{
      WhatIDo: WhatIDo,
    }
  }
}
</script>