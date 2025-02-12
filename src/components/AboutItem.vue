<template>
  <div style="margin-bottom: 20px">
    <h1 class="heading" style="margin-top: 6.25rem">About</h1>
    <div class="about-container">
      <div :class="!mobile ? 'about' : 'about m-container'">
        <p>
          My name is Sofia and I am 25 years old. In the summer of 2022, I
          finished my bachelor degree in ICT, media and design at Södertörn
          University. During my education I learned about programming, User
          interaction design, User interfaces and User friendly design. I also
          got knowledge about Adobe programs such as XD, Premiere pro,
          Illustrator and Indesign. I made a website to my relative. When making
          the website I followed the Design thinking process. I have worked at
          Wellfish as a Junior Frontend developer and UX designer. During my
          time at Wellfish, I learned more about UX design, Figma, User testing
          and User experience. I learned more about programming languages such
          as Vue.js, CSS, HTML, Javascript and Typescript. At Wellfish we worked
          with an agile method. We worked with programs such as Gitlab,
          Microsoft programs such as Exell and Power point.
        </p>
        <br />
        <p>
          I've studied programming at Distansakademin and Lexicon IT-proffs. At
          Distansakademin I learned about the following programming languages;
          C#, HTML, Javascript, .Net Core WebAPI/MVC, Entity framework, Node js
          and Vue.js. At Lexicon IT-proffs I got more knowledge about languages
          such as Javascript, Typescript, React and SCRUM. I had an internship
          at Traino as a frontend developer. At Traino, I got to help with their
          platform to bring trainers and fitness enthusiasts together. For now I
          study at IT högskolan and Företagsuniversitetet to gain more
          experience in AI, Python, informationsecurity and cybersecurity. It's
          fun to create websites and apps and to be able to be creative. It
          might be challenging but it is always fun to learn new things.
        </p>
        <br />
        <p>
          To see my projects within UX/UI, Frontend and Fullstack development go
          to "Projects".
        </p>
        <br />
        <p>
          I'm open for positions as a Frontend developer, UX/UI designer and
          Junior fullstack developer. If you are interested you are very welcome
          to contact me at; hjerpesofia@gmail.com or send a message to Linkedin
          at
          <a href="https://www.linkedin.com/in/sofia-hjerpe-17b171178/" style="color: #000100c9"
            >@Sofia Hjerpe</a
          >
          .<br /><br />
        </p>
        <p>Best Regards, <br />
          Sofia Hjerpe</p>
      </div>
      <SocialMediaItem :mobile="mobile" />
    </div>
    <div class="bachelor">
      <h3 class="heading" style="margin-bottom: 0">Degree certificate</h3>
      <img
        v-if="mobile"
        style="width: 300px; margin-top: 1em"
        src="../assets/images/Examensbevis.jpg"
      />
      <img
        v-if="mobile"
        style="width: 300px"
        src="../assets/images/Examensbevis1.jpg"
      />
      <img
        v-if="mobile"
        style="width: 300px"
        src="../assets/images/Examensbevis2.jpg"
      />
      <img
        v-if="mobile"
        style="width: 300px"
        src="../assets/images/Examensbevis3.jpg"
      />

      <img
        v-if="!mobile"
        style="width: 600px; margin-top: 1em"
        src="../assets/images/Examensbevis.jpg"
      />
      <img
        v-if="!mobile"
        style="width: 600px"
        src="../assets/images/Examensbevis1.jpg"
      />
      <img
        v-if="!mobile"
        style="width: 600px"
        src="../assets/images/Examensbevis2.jpg"
      />
      <img
        v-if="!mobile"
        style="width: 600px"
        src="../assets/images/Examensbevis3.jpg"
      />
    </div>
  </div>
</template>
<script>
import SocialMediaItem from "./SocialMediaItem.vue";

export default {
  name: "about",
  components: {
    SocialMediaItem,
  },
  props: {
    mobile: Boolean
  },

 
};
</script>

