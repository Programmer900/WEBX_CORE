<script setup lang="ts">
import { ref } from 'vue'
import { useHead } from '@vueuse/head'
import { useI18n } from 'vue-i18n'

import packageJson from '../../package.json'
import { useDarkmode } from '/@src/stores/darkmode'

type TabId = 'elements' | 'components' | 'forms' | 'plugins'
const activeTab = ref<TabId>('elements')
const darkmode = useDarkmode()

const { t } = useI18n()

useHead({
  title: 'WEBX GROUP - Investing in The Future',
})
</script>

<template>
  <MinimalLayout theme="light">
    <div class="landing-page-wrapper">
      <!-- Hero and Navbar -->
      <div id="vuero-landing" class="hero is-fullheight rounded-hero is-active">
        <!-- Navbar partial -->
        <LandingNavigation />
        <div class="absolute-header">
          <div class="header-inner">
            <div class='space'></div>

            <!--<img
              class="cut-circle light-image-l"
              src="/@src/assets/shapes/cut-circle.svg"
              alt=""
            />-->

          </div>
        </div>

        <div class="hero-body has-text-centered">
          <div class="container">

            <div class="switch-wrapper">
              <div class="night-toggle night-toggle--daynight">
                <input
                  id="night-toggle--daynight"
                  type="checkbox"
                  class="night-toggle--checkbox"
                  :checked="!darkmode.isDark"
                  aria-label="Toggle dark mode"
                  @change="darkmode.onChange"
                />
                <label
                  class="night-toggle--btn"
                  for="night-toggle--daynight"
                  tabindex="0"
                  @keydown.space.prevent="(e) => (e.target as HTMLLabelElement).click()"
                >
                  <span class="night-toggle--feature"></span>
                </label>
              </div>
              <h3 class="subtitle is-4 is-light">
                <span class="tag is-primary is-rounded">Beta 1.0<!--{{ packageJson.version }}--></span>
              </h3>
            </div>
            <p class="prev_title">{{ t('landing.top').toUpperCase() }}</p>
            <h1 class="title is-bold is-light is-bold">
              <span class="title-animation">WEBX GROUP</span>
            </h1>

            <p>
              <span class="subtitle-animation subtitle">{{ t('landing.slogan') }}</span>
            </p>
            <div class="spinner_wrapper">
            <div class="has-text-centered loader_2"><span style="--i:1"></span> <span style="--i:2"></span> <span style="--i:3"></span> <span style="--i:4"></span> <span style="--i:5"></span> <span style="--i:6"></span> <span style="--i:7"></span> <span style="--i:8"></span> <span style="--i:9"></span> <span style="--i:10"></span> <span style="--i:11"></span> <span style="--i:12"></span> <span style="--i:13"></span> <span style="--i:14"></span> <span style="--i:15"></span> <span style="--i:16"></span> <span style="--i:17"></span> <span style="--i:18"></span> <span style="--i:19"></span> <span style="--i:20"></span></div>
            </div>
          </div>
        </div>

        <div class="footer-copyright has-text-centered __absolute">
          <p>
            <span role="img" aria-label="copyright">&copy;</span> 2022 |
            <a to="/">WEBX GROUP</a> | All Rights Reserved.
          </p>
        </div>

      </div>

      <!--<div id="vuero-demos" class="section section-focus">
        <div class="container">
          &lt;!&ndash;Title&ndash;&gt;
          <div class="section-title has-text-centered">
            <h2 class="title is-2">Outstanding Demos</h2>
            <h4>Check out a wide variety of demo pages.</h4>
          </div>

          &lt;!&ndash;Demos partial&ndash;&gt;
          <LandingDemos />
        </div>
      </div>-->

      <!--Stacks Section-->
      <!--<div id="stacks-section" class="section">
        <div class="container">
          &lt;!&ndash;Stacks&ndash;&gt;
          <div class="stacks">
            <Tippy class="has-help-cursor" interactive placement="top">
              <div class="stack">
                <img src="/images/icons/stacks/vuejs.svg" alt="" />
              </div>
              <template #content>
                <StackPopoverContent
                  :stack="{
                    name: 'Vue 3',
                    subtitle: 'Composition API',
                    logo: '/images/icons/stacks/vuejs.svg',
                    description:
                      'The Progressive JavaScript Framework for building user interfaces.',
                    homepage: 'https://v3.vuejs.org/',
                    github: 'https://github.com/vuejs/vue-next',
                  }"
                />
              </template>
            </Tippy>

            <Tippy class="has-help-cursor" interactive placement="top">
              <div class="stack">
                <img src="/images/icons/stacks/vite.svg" alt="" />
              </div>
              <template #content>
                <StackPopoverContent
                  :stack="{
                    name: 'Vite',
                    subtitle: 'Next Generation Frontend Tooling',
                    logo: '/images/icons/stacks/vite.svg',
                    description:
                      'Vite is a new breed of frontend build tool that significantly improves the frontend development experience.',
                    homepage: 'https://vitejs.dev/',
                    github: 'https://github.com/vitejs/vite',
                  }"
                />
              </template>
            </Tippy>

            <Tippy class="has-help-cursor" interactive placement="top">
              <div class="stack">
                <img src="/images/icons/stacks/bulma.svg" alt="" />
              </div>
              <template #content>
                <StackPopoverContent
                  :stack="{
                    name: 'Bulma',
                    subtitle: 'The modern CSS framework',
                    logo: '/images/icons/stacks/bulma.svg',
                    description:
                      'Bulma is a free, open source framework that provides ready-to-use frontend components.',
                    homepage: 'https://bulma.io/',
                    github: 'https://github.com/jgthms/bulma',
                  }"
                />
              </template>
            </Tippy>

            <Tippy class="has-help-cursor" interactive placement="top">
              <div class="stack">
                <img src="/images/icons/stacks/sass.svg" alt="" />
              </div>
              <template #content>
                <StackPopoverContent
                  :stack="{
                    name: 'Sass',
                    subtitle: 'Makes CSS fun again',
                    logo: '/images/icons/stacks/sass.svg',
                    description:
                      'Sass is an extension of CSS, adding nested rules, variables, mixins, selector inheritance, and more.',
                    homepage: 'https://sass-lang.com/',
                    github: 'https://github.com/sass/sass',
                  }"
                />
              </template>
            </Tippy>

            <Tippy class="has-help-cursor" interactive placement="top">
              <div class="stack">
                <img src="/images/icons/stacks/typescript.svg" alt="" />
              </div>
              <template #content>
                <StackPopoverContent
                  :stack="{
                    name: 'Typescript',
                    subtitle: 'Javascript enhanced',
                    logo: '/images/icons/stacks/typescript.svg',
                    description:
                      'TypeScript adds optional types to JavaScript that support tools for large-scale JavaScript applications.',
                    homepage: 'https://www.typescriptlang.org/',
                    github: 'https://github.com/microsoft/TypeScript',
                  }"
                />
              </template>
            </Tippy>
          </div>

          &lt;!&ndash;Title&ndash;&gt;
          <div class="section-title has-text-centered">
            <h2 class="title is-2">Amazing Features</h2>
            <h4>All you need to build your project is there.</h4>
          </div>

          &lt;!&ndash;Boxed Features&ndash;&gt;
          <div class="boxed-features">
            <div class="flex-card light-bordered hover-inset">
              <div class="flex-cell is-bordered">
                <i aria-hidden="true" class="lnil lnil-toolbox"></i>
                <h3>500+ Vue Components</h3>
                <p>An incredible set of building blocks with dark mode support.</p>
              </div>
              <div class="flex-cell is-bordered">
                <i aria-hidden="true" class="lnil lnil-display-alt"></i>
                <h3>220+ Demos</h3>
                <p>Vuero ships with a huge number of demos to kickstart your project.</p>
              </div>
              <div class="flex-cell is-bordered">
                <i aria-hidden="true" class="lnil lnil-moon"></i>
                <h3>Native Dark Mode</h3>
                <p>Every single piece of UI is natively dark mode ready.</p>
              </div>
              <div class="flex-cell is-bordered no-border-edge">
                <i aria-hidden="true" class="lnil lnil-rocket"></i>
                <h3>Active Support</h3>
                <p>Our support helps you solve any issues you have</p>
              </div>
              <div class="flex-cell">
                <i aria-hidden="true" class="lnil lnil-code"></i>
                <h3>Clean Code</h3>
                <p>Vuero's codebase is huge, but structured and easy to understand</p>
              </div>
              <div class="flex-cell">
                <i aria-hidden="true" class="lnil lnil-plug"></i>
                <h3>Premium Icons</h3>
                <p>Vuero ships with the premium Line Icons set ($30 value).</p>
              </div>
              <div class="flex-cell">
                <i aria-hidden="true" class="lnil lnil-mobile-alt-2"></i>
                <h3>Fully Responsive</h3>
                <p>Vuero is built with Bulma 0.9, a mobile first framework</p>
              </div>
              <div class="flex-cell no-border-edge">
                <i aria-hidden="true" class="lnil lnil-file-name"></i>
                <h3>Extensive Docs</h3>
                <p>A nice documentation to help you get started fast</p>
              </div>
            </div>
          </div>

          &lt;!&ndash;Title&ndash;&gt;
          <div class="section-title has-text-centered">
            <h2 class="title is-2">Developer Experience</h2>
            <h4>A set of professional tools to build professional apps.</h4>
          </div>

          &lt;!&ndash;Boxed Features&ndash;&gt;
          <div class="boxed-features is-flat pb-6">
            <div class="flex-card light-bordered hover-inset">
              <div class="flex-cell is-bordered">
                <img src="/images/icons/stacks/vuejs-solo.svg" alt="" />
                <h3>Vue 3</h3>
                <p>
                  Vue 3 and its powerful composition API makes your experience pleasant.
                </p>
              </div>
              <div class="flex-cell">
                <img src="/images/icons/stacks/typescript-square.svg" alt="" />
                <h3>Typescript</h3>
                <p>Typescript makes things much more simpler but remains optional.</p>
              </div>
              <div class="flex-cell is-bordered">
                <img src="/images/icons/stacks/vite.svg" alt="" />
                <h3>Vite JS</h3>
                <p>
                  Vite 2 is blazing fast, does HOT reloading and parses all your
                  components.
                </p>
              </div>
              <div class="flex-cell">
                <img src="/images/icons/stacks/vscode.svg" alt="" />
                <h3>VS Code Integration</h3>
                <p>
                  Vuero is fully integrated with VS Code to help you produce quality
                  checked code.
                </p>
              </div>
              <div class="flex-cell is-bordered">
                <img src="/images/icons/stacks/eslint.svg" alt="" />
                <h3>ES Lint</h3>
                <p>
                  ES Lint watches your javascript code and makes sure it matches the best
                  standards.
                </p>
              </div>
              <div class="flex-cell is-bordered">
                <img src="/images/icons/stacks/prettier.svg" alt="" />
                <h3>Prettier</h3>
                <p>
                  Prettier tidies your code and makes it look much more cleaner and easier
                  to read.
                </p>
              </div>
              <div class="flex-cell">
                <img
                  class="light-image-block-l"
                  src="/images/icons/stacks/stylelint.svg"
                  alt=""
                />
                <img
                  class="dark-image-block-l"
                  src="/images/icons/stacks/stylelint-reverse.svg"
                  alt=""
                />
                <h3>Stylelint</h3>
                <p>
                  Stylelint looks for poorly formatted styles and fixes everything for
                  you.
                </p>
              </div>
              <div class="flex-cell">
                <img src="/images/icons/stacks/iconify.svg" alt="" />
                <h3>Iconify</h3>
                <p>
                  Iconify displays icons inside your code editor so you always know what
                  you're doing.
                </p>
              </div>
              <div class="flex-cell">
                <img src="/images/icons/stacks/cypress.svg" alt="" />
                <h3>Cypress</h3>
                <p>
                  Cypress handles end to end testing to make sure everything works as
                  expected.
                </p>
              </div>
              <div class="flex-cell">
                <img src="/images/icons/stacks/pnpm-yarn.svg" alt="" />
                <h3>Pnpm + Yarn</h3>
                <p>
                  Vuero works very well with Pnpm or Yarn for efficient dependency
                  management.
                </p>
              </div>
              <div class="flex-cell">
                <img src="/images/icons/stacks/docker-whale.svg" alt="" />
                <h3>Docker</h3>
                <p>
                  Vuero ships with a Docker file to make your test deployments faster and
                  easier.
                </p>
              </div>
              <div class="flex-cell">
                <img src="/images/icons/stacks/robot.svg" alt="" />
                <h3>Robot Friendly</h3>
                <p>
                  Fully featured with structured data. Help your site display in richer
                  features in search results.
                </p>
              </div>
              <div class="flex-cell">
                <img src="/images/icons/misc/success.svg" alt="" />
                <h3>Props Validation</h3>
                <p>
                  Vuero base components ship with props validation to prevent unexpected
                  errors.
                </p>
              </div>
              <div class="flex-cell">
                <img src="/images/icons/misc/error.svg" alt="" />
                <h3>Error Handling</h3>
                <p>
                  While developping Vuero, we focused on providing an up to standards
                  error handling.
                </p>
              </div>
              <div class="flex-cell">
                <img src="/images/icons/misc/folder.svg" alt="" />
                <h3>Project Structure</h3>
                <p>
                  A clean and organized project structure lets you find any file or
                  content quickly.
                </p>
              </div>
              <div class="flex-cell">
                <img src="/images/icons/misc/documentation.svg" alt="" />
                <h3>Component Guide</h3>
                <p>
                  A full component / plugin documentation with a lot of code examples
                  lives inside Vuero.
                </p>
              </div>
            </div>
          </div>

          &lt;!&ndash;CTA&ndash;&gt;
          <div class="cta-block">
            <div class="head-text">
              <h3>Buy Vuero</h3>
              <p>Available on Envato Market</p>
            </div>
            <div class="head-action">
              <div class="buttons">
                <a
                  href="https://themeforest.net/item/vuero-vuejs-3-admin-and-webapp-ui-kit/31053035"
                  class="button v-button is-primary is-rounded is-elevated action-button"
                >
                  Buy Now
                </a>
                <a href="https://cssninja.io" class="button chat-button">
                  Chat with us
                </a>
              </div>
            </div>
          </div>


          &lt;!&ndash;Title&ndash;&gt;
          <div class="section-title has-text-centered">
            <h2 class="title is-2">Get started with Vuero</h2>
            <h4>
              Watch the quickstart tutorial and access our private Discord and GitHub
              repo.
            </h4>

            <div class="mt-4">
              <VButtons align="centered">
                <VButton
                  href="https://discord.cssninja.io/"
                  icon="fa-brands:discord"
                  dark-outlined
                  raised
                >
                  Discord Access
                </VButton>
                <VButton
                  v-tooltip.top.rounded="
                    'Send us your GitHub username at https://support.cssninja.io'
                  "
                  icon="fa-brands:github"
                  style="cursor: help"
                  dark-outlined
                  raised
                >
                  GitHub Access
                </VButton>
              </VButtons>
            </div>
          </div>

          <div class="video-player-container-wrapper mb-6">
            <VPlyr
              ratio="16by9"
              source="https://www.youtube.com/embed/lE5VNpP8JqA?modestbranding=1&rel=0&showinfo=0"
              poster="/video/poster-2c.jpg"
              title="VUERO | part 1 - Cleaning the project and getting started"
              embed
            />
          </div>
        </div>
      </div>-->

      <!--Side Features Section-->
      <!--<div class="section">
        <div class="container">
          &lt;!&ndash;Title&ndash;&gt;
          <div class="section-title has-text-centered">
            <h2 class="title is-2">Top Tier Product</h2>
            <h4>Vuero has been carefully handcrafted.</h4>
          </div>

          &lt;!&ndash; Feature &ndash;&gt;
          <div class="columns is-vcentered side-feature">
            <div class="column is-6 has-text-centered">
              <img
                class="light-image-l featured-image"
                src="/@src/assets/illustrations/landing/feature-1.png?width=560&height=406&format=webp"
                alt=""
              />
              <img
                class="dark-image-l featured-image"
                src="/@src/assets/illustrations/landing/feature-1-dark.png?width=560&height=406&format=webp"
                alt=""
              />
            </div>
            <div class="column is-5">
              <h2 class="title m-b-10 is-centered-tablet-portrait">Incredible UI</h2>
              <p class="section-feature-description is-centered-tablet-portrait">
                Vuero's UI has been carefully thought and designed, and is simply one of
                the best you'll find on the market. It's visual power and its modularity
                will let you build great apps seamlessly.
              </p>
            </div>
          </div>
          &lt;!&ndash; Feature &ndash;&gt;
          <div class="columns is-vcentered side-feature">
            <div class="column is-6 has-text-centered h-hidden-desktop h-hidden-tablet-p">
              <img
                class="light-image-l featured-image"
                src="/@src/assets/illustrations/landing/feature-2.svg"
                alt=""
              />
              <img
                class="dark-image-l featured-image"
                src="/@src/assets/illustrations/landing/feature-2-dark.svg"
                alt=""
              />
            </div>
            <div class="column is-5 is-offset-1">
              <h2 class="title m-b-10 is-centered-tablet-portrait">Playful Vectors</h2>
              <p class="section-feature-description is-centered-tablet-portrait">
                Vuero ships with a lot of svg illustrations representing various elements
                that can be used in a website, following very high quality standards.
              </p>
            </div>
            <div class="column is-6 has-text-centered h-hidden-mobile">
              <img
                class="light-image-l featured-image"
                src="/@src/assets/illustrations/landing/feature-2.svg"
                alt=""
              />
              <img
                class="dark-image-l featured-image"
                src="/@src/assets/illustrations/landing/feature-2-dark.svg"
                alt=""
              />
            </div>
          </div>
          &lt;!&ndash; Feature &ndash;&gt;
          <div class="columns is-vcentered side-feature">
            <div class="column is-6 has-text-centered">
              <img
                class="light-image-l featured-image"
                src="/@src/assets/illustrations/landing/feature-3.svg"
                alt=""
              />
              <img
                class="dark-image-l featured-image"
                src="/@src/assets/illustrations/landing/feature-3-dark.svg"
                alt=""
              />
            </div>
            <div class="column is-5">
              <h2 class="title m-b-10 is-centered-tablet-portrait">Handcrafted UI</h2>
              <p class="section-feature-description is-centered-tablet-portrait">
                Vuero ships with it's own component library based on the Bulma.io CSS
                framework. Each component has been carefully handcrafted and natively
                supports dark mode.
              </p>
            </div>
          </div>

          &lt;!&ndash;CTA&ndash;&gt;
          <div class="cta-block no-border">
            <div class="head-text">
              <h3>Want to learn more?</h3>
              <p>Check out the Vuero documentation</p>
            </div>
            <div class="head-action">
              <div class="buttons">
                <a
                  href="https://docs.cssninja.io/vuero"
                  class="button v-button is-primary is-rounded is-elevated action-button"
                >
                  Read the Docs
                </a>
                <a href="https://cssninja.io" class="button chat-button is-secondary">
                  Chat with us
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>-->

      <!--<div id="vuero-components" class="section section-focus">
        <div class="container">
          <div class="columns is-vcentered">
            <div class="column is-6 is-offset-3 has-text-centered">
              &lt;!&ndash;Title&ndash;&gt;
              <div class="section-title has-text-centered p-b-40">
                <h2 class="title is-3">Reusable components</h2>
                <h4>Vuero ships with a full component library.</h4>
              </div>
            </div>
          </div>
          <div class="columns is-vcentered component-features is-flex-tablet-p">
            <div class="column is-4">
              &lt;!&ndash; Side icon box &ndash;&gt;
              <div class="media-flex">
                <div class="left-icon">
                  <i aria-hidden="true" class="lnil lnil-construction"></i>
                </div>
                <div class="flex-meta">
                  <h4>Modular</h4>
                  <p>
                    Vuero uses a modular CSS structure leveraging the power of Sass. Each
                    component family has it's own files and encapsulated styles.
                  </p>
                </div>
              </div>
            </div>
            <div class="column is-4">
              &lt;!&ndash; Side icon box &ndash;&gt;
              <div class="media-flex">
                <div class="left-icon">
                  <i aria-hidden="true" class="lnil lnil-code"></i>
                </div>
                <div class="flex-meta">
                  <h4>Code Blocks</h4>
                  <p>
                    A lot of code examples are provided out of the box with syntax
                    highlighting. Building your app layout is a simple as copying and
                    pasting.
                  </p>
                </div>
              </div>
            </div>
            <div class="column is-4">
              &lt;!&ndash; Side icon box &ndash;&gt;
              <div class="media-flex">
                <div class="left-icon">
                  <i aria-hidden="true" class="lnil lnil-color-palette"></i>
                </div>
                <div class="flex-meta">
                  <h4>Easy Theming</h4>
                  <p>
                    Vuero's components provide easy to use class based color variations
                    and modifiers to help you write less CSS. Theming is also very easy.
                  </p>
                </div>
              </div>
            </div>
          </div>

          &lt;!&ndash;CTA&ndash;&gt;
          <p class="p-t-40 p-b-40 has-text-centered">
            <a
              href="https://themeforest.net/item/vuero-vuejs-3-admin-and-webapp-ui-kit/31053035"
              class="button v-button is-rounded is-primary is-elevated is-bold is-huge"
            >
              Buy Now
            </a>
          </p>

          &lt;!&ndash;Components&ndash;&gt;
          <div class="vuero-components p-t-40 p-b-60">
            <div class="vertical-tabs-wrapper">
              <div class="tabs">
                <ul>
                  <li :class="[activeTab === 'elements' && 'is-active']">
                    <a
                      tabindex="0"
                      @keydown.space.prevent="activeTab = 'elements'"
                      @click="activeTab = 'elements'"
                    >
                      Elements
                    </a>
                  </li>
                  <li :class="[activeTab === 'components' && 'is-active']">
                    <a
                      tabindex="0"
                      @keydown.space.prevent="activeTab = 'components'"
                      @click="activeTab = 'components'"
                    >
                      Components
                    </a>
                  </li>
                  <li :class="[activeTab === 'forms' && 'is-active']">
                    <a
                      tabindex="0"
                      @keydown.space.prevent="activeTab = 'forms'"
                      @click="activeTab = 'forms'"
                    >
                      Forms
                    </a>
                  </li>
                  <li :class="[activeTab === 'plugins' && 'is-active']">
                    <a
                      tabindex="0"
                      @keydown.space.prevent="activeTab = 'plugins'"
                      @click="activeTab = 'plugins'"
                    >
                      Plugins
                    </a>
                  </li>
                </ul>
              </div>
              <div class="content-wrap">
                <LandingComponents :active-tab="activeTab" />
              </div>
            </div>
          </div>
        </div>
      </div>-->

     <!--<div class="section">
        <div class="container">
          &lt;!&ndash;Title&ndash;&gt;
          <div class="section-title has-text-centered pt-40">
            <h2 class="title is-3">3 More Reasons To Choose Vuero</h2>
            <h4>If you're not convinced yet, here's some more.</h4>
          </div>

          <div class="customers-choice p-t-40 p-b-40">
            &lt;!&ndash; Feature &ndash;&gt;
            <div class="columns is-vcentered side-feature">
              <div class="column is-5 is-offset-1 has-text-centered">
                <img
                  class="light-image-l featured-image"
                  src="/@src/assets/illustrations/landing/feature-4.svg"
                  alt=""
                />
                <img
                  class="dark-image-l featured-image"
                  src="/@src/assets/illustrations/landing/feature-4-dark.svg"
                  alt=""
                />
              </div>
              <div class="column is-5">
                <h2 class="title m-b-10 is-centered-tablet-portrait">Professional</h2>
                <p class="section-feature-description is-centered-tablet-portrait">
                  Vuero is a professional product to build professional applications.
                  You'll find everything you need to build a project that is up to the
                  highest standards of web development.
                </p>
              </div>
            </div>

            &lt;!&ndash; Feature &ndash;&gt;
            <div class="columns is-vcentered side-feature">
              <div
                class="column is-5 has-text-centered h-hidden-desktop h-hidden-tablet-p"
              >
                <img
                  class="light-image-l featured-image"
                  src="/@src/assets/illustrations/landing/feature-5.svg"
                  alt=""
                />
                <img
                  class="dark-image-l featured-image"
                  src="/@src/assets/illustrations/landing/feature-5-dark.svg"
                  alt=""
                />
              </div>
              <div class="column is-5 is-offset-1">
                <h2 class="title m-b-10 is-centered-tablet-portrait">Fast Development</h2>
                <p class="section-feature-description is-centered-tablet-portrait">
                  Vuero ships with a Vitejs development server that will assist you when
                  customizing the template. It handles .vue files compilation as well as
                  SCSS and Typescript code. The page is refreshed each time you hit the
                  save trigger in your favorite editor.
                </p>
              </div>
              <div class="column is-5 has-text-centered h-hidden-mobile">
                <img
                  class="light-image-l featured-image"
                  src="/@src/assets/illustrations/landing/feature-5.svg"
                  alt=""
                />
                <img
                  class="dark-image-l featured-image"
                  src="/@src/assets/illustrations/landing/feature-5-dark.svg"
                  alt=""
                />
              </div>
            </div>

            &lt;!&ndash; Feature &ndash;&gt;
            <div class="columns is-vcentered side-feature">
              <div class="column is-5 is-offset-1 has-text-centered">
                <img
                  class="light-image-l featured-image"
                  src="/@src/assets/illustrations/landing/feature-6.svg"
                  alt=""
                />
                <img
                  class="dark-image-l featured-image"
                  src="/@src/assets/illustrations/landing/feature-6-dark.svg"
                  alt=""
                />
              </div>
              <div class="column is-5">
                <h2 class="title m-b-10 is-centered-tablet-portrait">
                  Extensive Documentation
                </h2>
                <p class="section-feature-description is-centered-tablet-portrait">
                  Vuero's documentation will be a precious ally, as the template has a
                  large codebase, and a lot of files. Read carefully the docs, all you
                  need to know for an optimal development experience is there, even if you
                  still are a beginner.
                </p>
              </div>
            </div>
          </div>

          <div class="cta-wrapper">
            <div class="cta-title">
              <h3>Exclusively on Envato Market</h3>
              <a
                href="https://themeforest.net/item/vuero-vuejs-3-admin-and-webapp-ui-kit/31053035"
                class="custom-button"
              >
                <img src="/images/icons/logos/envato.svg" alt="" />
                <span>Get It Now</span>
              </a>
            </div>
          </div>
        </div>
      </div>-->

      <LanguagesPanel />

      <!-- Footer -->
      <!--<LandingFooter />-->

      <!-- Desktop navigation -->
      <CircularMenu />


      <!-- Back To Top Button -->
      <div id="backtotop">
        <a href="#" aria-label="back to top">
          <i aria-hidden="true" class="fas fa-angle-up"></i>
        </a>
      </div>
    </div>
  </MinimalLayout>
</template>

<style lang="scss">
@import '../scss/abstracts/mixins';
@import '../scss/_demo/landing';

#circular-menu {
  top: 50%;
  transform: translate(0, -50%);
}

/* Animations */
@-webkit-keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

/* Space */
.space {
  position: absolute;
  width: 400vw;
  height: 400vh;
  top: 50%;
  left: 50%;
  margin-top: -200vh;
  margin-left: -200vw;
  -webkit-animation: spin 240s linear infinite;
  animation: spin 240s linear infinite;
  background-size: 240px;
  -webkit-backface-visibility: visible;
  backface-visibility: visible;
  /* Had to base64 SVG background for FF compatibility */
  background-image: url(data:image/svg+xml;base64,PHN2ZyB2ZXJzaW9uPSIxLjEiIGlkPSJMYXllcl8yIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB4PSIwcHgiIHk9IjBweCIgdmlld0JveD0iMCAwIDI0MCAyNDAiIGVuYWJsZS1iYWNrZ3JvdW5kPSJuZXcgMCAwIDI0MCAyNDAiIHhtbDpzcGFjZT0icHJlc2VydmUiPjxyZWN0IHg9IjEwNiIgeT0iOTAiIGZpbGw9IiNGRkZGRkYiIHdpZHRoPSIyIiBoZWlnaHQ9IjIiLz48cmVjdCB4PSI3NCIgeT0iNjMiIGZpbGw9IiNGRkZGRkYiIHdpZHRoPSIxIiBoZWlnaHQ9IjEiLz48cmVjdCB4PSIyMyIgeT0iNjYiIGZpbGw9IiNGRkZGRkYiIHdpZHRoPSIxIiBoZWlnaHQ9IjEiLz48cmVjdCB4PSI1MCIgeT0iMTEwIiBmaWxsPSIjRkZGRkZGIiB3aWR0aD0iMSIgaGVpZ2h0PSIxIi8+PHJlY3QgeD0iNjMiIHk9IjEyOCIgZmlsbD0iI0ZGRkZGRiIgd2lkdGg9IjEiIGhlaWdodD0iMSIvPjxyZWN0IHg9IjQ1IiB5PSIxNDkiIGZpbGw9IiNGRkZGRkYiIHdpZHRoPSIxIiBoZWlnaHQ9IjEiLz48cmVjdCB4PSI5MiIgeT0iMTUxIiBmaWxsPSIjRkZGRkZGIiB3aWR0aD0iMSIgaGVpZ2h0PSIxIi8+PHJlY3QgeD0iNTgiIHk9IjgiIGZpbGw9IiNGRkZGRkYiIHdpZHRoPSIxIiBoZWlnaHQ9IjEiLz48cmVjdCB4PSIxNDciIHk9IjMzIiBmaWxsPSIjRkZGRkZGIiB3aWR0aD0iMiIgaGVpZ2h0PSIyIi8+PHJlY3QgeD0iOTEiIHk9IjQzIiBmaWxsPSIjRkZGRkZGIiB3aWR0aD0iMSIgaGVpZ2h0PSIxIi8+PHJlY3QgeD0iMTY5IiB5PSIyOSIgZmlsbD0iI0ZGRkZGRiIgd2lkdGg9IjEiIGhlaWdodD0iMSIvPjxyZWN0IHg9IjE4MiIgeT0iMTkiIGZpbGw9IiNGRkZGRkYiIHdpZHRoPSIxIiBoZWlnaHQ9IjEiLz48cmVjdCB4PSIxNjEiIHk9IjU5IiBmaWxsPSIjRkZGRkZGIiB3aWR0aD0iMSIgaGVpZ2h0PSIxIi8+PHJlY3QgeD0iMTM4IiB5PSI5NSIgZmlsbD0iI0ZGRkZGRiIgd2lkdGg9IjEiIGhlaWdodD0iMSIvPjxyZWN0IHg9IjE5OSIgeT0iNzEiIGZpbGw9IiNGRkZGRkYiIHdpZHRoPSIzIiBoZWlnaHQ9IjMiLz48cmVjdCB4PSIyMTMiIHk9IjE1MyIgZmlsbD0iI0ZGRkZGRiIgd2lkdGg9IjIiIGhlaWdodD0iMiIvPjxyZWN0IHg9IjEyOCIgeT0iMTYzIiBmaWxsPSIjRkZGRkZGIiB3aWR0aD0iMSIgaGVpZ2h0PSIxIi8+PHJlY3QgeD0iMjA1IiB5PSIxNzQiIGZpbGw9IiNGRkZGRkYiIHdpZHRoPSIxIiBoZWlnaHQ9IjEiLz48cmVjdCB4PSIxNTIiIHk9IjIwMCIgZmlsbD0iI0ZGRkZGRiIgd2lkdGg9IjEiIGhlaWdodD0iMSIvPjxyZWN0IHg9IjUyIiB5PSIyMTEiIGZpbGw9IiNGRkZGRkYiIHdpZHRoPSIyIiBoZWlnaHQ9IjIiLz48cmVjdCB5PSIxOTEiIGZpbGw9IiNGRkZGRkYiIHdpZHRoPSIxIiBoZWlnaHQ9IjEiLz48cmVjdCB4PSIxMTAiIHk9IjE4NCIgZmlsbD0iI0ZGRkZGRiIgd2lkdGg9IjEiIGhlaWdodD0iMSIvPjwvc3ZnPg==);
}

/*Custom Page Home Styles*/
#vuero-demos {
  z-index: 0;
}

html:not(.is-dark) #app.app-wrapper .light .space {
  //display: none;
}
html:not(.is-dark) .absolute-header, html:not(.is-dark) #languages-panel .right-panel {
  background-color: #244468;
  //background-color: #183154;
}

html:not(.is-dark) .right-panel-wrapper.is-languages .right-panel-body .languages-boxes .language-box .language-option .language-option-inner {
  border: 1.0px solid #244468;
  background: #1c3a5c;
}

.right-panel-wrapper.is-languages .right-panel-body .languages-boxes .language-box .language-option .language-option-inner .indicator {
  border: none;
}
html:not(.is-dark) h1 {
  background: -webkit-linear-gradient(white, #dbdde0, #38495a);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.title-animation, h1.title {
  display: block;
  font-weight: 300;
  margin-top: 10px;
  font-size: 65px;
  text-align: center;
  letter-spacing: 5px;
  background: -webkit-linear-gradient(white, #dbdde0, #38495a);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation-duration: 6s;
  animation-iteration-count: 1;
  animation-timing-function: ease;
  animation-name: animGravity;
}

.prev_title {
  display: block;
  background: -webkit-linear-gradient(white, #dbdde0, #38495a);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation-duration: 4s;
  animation-iteration-count: 1;
  animation-timing-function: ease;
  animation-name: animGravity;
}

html:not(.is-dark) .title-animation {
  /*background: -webkit-linear-gradient(white, #38495a, #38495a);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;*/
}

.subtitle-animation {
  display: block;
  font-weight: 300;
  margin-top: 10px;
  font-size: 40px;
  text-align: center;
  letter-spacing: 5px;
  background: -webkit-linear-gradient(white, #dbdde0, #38495a);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation-duration: 6s;
  animation-iteration-count: 1;
  animation-timing-function: ease;
  animation-name: animGravity;
}

html:not(.is-dark) .subtitle-animation  {
  /*background: -webkit-linear-gradient(white, #38495a, #38495a);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;*/
}

@keyframes animGravity {
  0% {
    opacity: 0;
  }
  30% {
    opacity: 0.3;
  }

  50% {
    opacity: 0.5;
  }

  80% {
    opacity: 0.8;
  }

  100% {
    opacity: 1;
  }

}

  .switch-wrapper {
    position: fixed;
    right: 0;
    bottom: 2%;
  }

  /*Loader*/
.loader_2 span {
  position: absolute;
  top: 0;
  left: 50%;
  width: 20px;
  height: 20px;
  transform: rotate(calc(18deg * var(--i))) translate(-50%, -50%);
}
.loader_2 span::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background: #0c5460;
  box-shadow: 0 0 10px #1c559a, 0 0 20px #1c559a, 0 0 40px #1c559a, 0 0 60px #1c559a, 0 0 80px #1c559a, 0 0 100px #1c559a, 0 0 120px #1c559a;
  animation: animate 2s linear infinite;
  animation-delay: calc(0.1s * var(--i));
}

html:not(.is-dark) .loader_2 span::before {
  background: #e5e5e7;
  box-shadow: 0 0 10px #e5e5e7, 0 0 20px #e5e5e7, 0 0 40px #e5e5e7, 0 0 60px #e5e5e7, 0 0 80px #1c559a, 0 0 100px #1c559a, 0 0 120px #1c559a;
}

.prev_title {
  font-size: 1.4em;
}

.spinner_wrapper {
  width: 100%;
  text-align: center;
  margin-top: 60px;
  animation-duration: 6s;
  animation-iteration-count: 1;
  animation-timing-function: ease;
  animation-name: animGravity;
}
.loader_2 {
  position: relative;
  width: 100%;
  height: 45px;
  margin-top: 15px;
  -webkit-animation: animateBg 10s linear infinite, showDiv 3s ease;
  -moz-animation: animateBg 10s linear infinite, showDiv 3s ease;
  -ms-animation: animateBg 10s linear infinite, showDiv 3s ease;
  -o-animation: animateBg 10s linear infinite, showDiv 3s ease;
  animation: animateBg 10s linear infinite, showDiv 3s ease;
}

@keyframes showDiv {
  0% {
    opacity: 0;
  }
  10% {
    opacity: 0;
  }
  20% {
    opacity: 0;
  }
  30% {
    opacity: 0.3;
  }
  40% {
    opacity: 0.4;
  }
  50% {
    opacity: 0.5;
  }
  60% {
    opacity: 0.6;
  }
  70% {
    opacity: 0.7;
  }
  80% {
    opacity: 0.8;
  }
  90% {
    opacity: 0.9;
  }
  100% {
    opacity: 1;
  }
}
@keyframes animateBg {
  0% {
    filter: hue-rotate(0);
  }
  100% {
    filter: hue-rotate(0);
  }
}
@keyframes animate {
  0% {
    transform: scale(1);
  }
  100%,
  80% {
    transform: scale(0);
  }
}

.footer-copyright.__absolute {
  position: absolute;
  bottom: 2%;
  left: 50%;
  transform: translate(-50%, 0);
}

@media screen and(max-width: 1020px) {
  html:not(.is-dark) #vuero-landing .navbar-burger {
    background: #283252;
  }

  html:not(.is-dark) #vuero-landing .navbar-burger span{
    background: #fff;
  }
}
@media screen and(max-width: 768px) {
  #vuero-landing {
    height: 100vh;
    min-height: auto;
    max-height: 100vh;
  }

  .landing-page-wrapper .rounded-hero .hero-body h1 {
    font-size: 1.2rem !important;
  }
  .subtitle-animation {
    font-size: 1.1rem !important;
  }
  .landing-page-wrapper .rounded-hero .absolute-header {
    height: 100vh;
    overflow: hidden;
  }

  .title-animation {
    margin-bottom: 0px !important;
  }
  h1.title {
    margin-bottom: 0 !important;
  }

}
@media screen and(max-width: 620px) {
  .title-animation {
    font-size: 2.5em !important;
    margin-bottom: 5px !important;
  }
}

@media screen and(max-width: 400px) {
  .title-animation {
    font-size: 2.0em !important;
    margin-bottom: 0px !important;
  }
  h1.title {
    margin-bottom: 0 !important;
  }
  .subtitle-animation {
    font-size: .8em !important;
  }
}

</style>
