<template>
  <div id="app">
    <div
      class="header"
    >
      <div>
        <img
          src="@/svg/logo.svg"
          class="logo"
        >
      </div>
      <div class="logo-text">
        Terra infinity
      </div>
    </div>

    <div class="body">
      <ScrollButton/>
      <TechBlock/>
      <div class="fullpage-container">
        <div
          v-fullpage="opts"
          class="fullpage-wp"
        >
          <div
            v-for="(page, i) in pages"
            :key="i"
            :class="[page.class]"
            class="page" 
          >
            <div v-animate="{value: 'fadeInUp'}">
              <div
                v-html="page.title"
                class="title"
              ></div>
              <div
                v-html="page.desk"
                class="desk"
              ></div>
              <div v-animate="{value: 'fadeInUp', delay: 900}">
                <div
                  v-text="page.actionText"
                  class="action"
                ></div>
                <div
                  v-text="page.email"
                  class="email"
                ></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ScrollButton from '@/components/ScrollButton.vue';
import TechBlock from '@/components/TechBlock.vue';

export default {
  components: {
    ScrollButton,
    TechBlock
  },
  data() {
    return {
      pages: [
        {
          title: 'Digitalization<br/>and user experiennce',
          class: 'page-1',
          desk: `
            Using our multi industry experience we will analyse<br/>
            your status quo and help you build new digital<br/>
            solutions for your business, which will give you<br/>
            that edge over your competitors.<br/>
            Great user experience is increasingly important<br/>
            in the modern world - we will help you to achieve<br/>
            the magic.
          `,
          actionText: 'write us:',
          email: 'dugitalize@terrainfinity.com'
        },
        {
          title: 'Remote<br/>product team',
          class: 'page-2',
          desk: `
            According to your needs we will build in a very short<br/>
            time frame a near-shore remote team of the excellent<br/>
            professionals, which will solve your problem and<br/>
            deliver a solution.<br/>
            We will be responsible for setting up agile processes<br/>
            and will guide the team. Outsourcing has never been<br/>
            easier.
          `,
          actionText: 'Get in touch:',
          email: 'remote@terrainfinity.com'
        },
        {
          title: 'Software<br/>development',
          class: 'page-3',
          desk: `
            Over the years we created different software with different<br/>
            technologies for different purposes. For small companies<br/>
            and for big enterprises. From games to financial solutions.<br/>
            We are proud to have some of the biggest companies in the<br/>
            world among our customers. Our mobile apps won multiply<br/>
            awards and were featured many times by Apple.<br/>
          `,
          actionText: 'Click here:',
          email: 'software@terrainfinity.com'
        },
        {
          title: 'Software<br/>development',
          class: 'page-4',
          desk: `
            We excel in doing research and prototypes.<br/>
            We have years of experience in different areas: apps,<br/>
            branding, ux, finance, games, video and more.<br/>
            If you got an idea, a problem, not sure how to proceed, need<br/>
            to get a feeling for something - we will help.<br/>
          `,
          actionText: 'Write here:',
          email: 'rd@terrainfinity.com'
        }
      ],

      opts: {
        start: 0,
        dir: 'v',
        duration: 500,
        beforeChange: (prev, next) => {},
        afterChange: (prev, next) => {}
      }
    }
  }
}
</script>

<style lang="scss">
  @import "./css/main.css";
</style>