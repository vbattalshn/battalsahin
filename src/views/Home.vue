<template>
  <AboutMe />
  <Title count="01" title="Neler Yaparım?" />
  <WhatIDo />
  <Title count="02" title="Bildiklerim" />
  <MySkills />
  <Title count="03" title="Projelerim" />
  <MyProjects />
  <Title count="05" title="Hakkımda Ne Söylüyolar?" />
  <Comments />
  <Title count="04" title="Bana Yazın" />
  <WriteMe />
</template>

<script>
import Title from "../components/UI/Title"
import AboutMe from "../components/AboutMe"
import WhatIDo from "../components/WhatIDo"
import MySkills from "../components/MySkills"
import MyProjects from "../components/MyProjects"
import Comments from "../components/Comments"
import WriteMe from "../components/WriteMe"

export default{
  components: { AboutMe, Title, WhatIDo, MySkills, MyProjects, Comments, WriteMe }
}

</script>
