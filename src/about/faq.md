# Questões Feitas Frequentemente {#frequently-asked-questions}

## Quem mantém a Vue? {#who-maintains-vue}

Vue é um projeto independente e voltado para a comunidade. Foi criada por [Evan You](https://twitter.com/youyuxi) em 2014 como um projeto paralelo pessoal. Hoje, a Vue é mantida ativamente por [uma equipa de membros em tempo integral e voluntários de todo o mundo](/about/team), em que Evan atua como o líder do projeto. Tu podes aprender mais sobre a história da Vue neste [documentário](https://www.youtube.com/watch?v=OrxmtDw4pVI).

O desenvolvimento da Vue é financiado principalmente por meio de patrocínios. Se tu ou tua empresa se beneficiam da Vue, considere [nos patrocinar](/sponsor/) para apoiar o desenvolvimento da Vue!

## Qual a diferença entre a Vue 2 e a Vue 3? {#what-s-the-difference-between-vue-2-and-vue-3}

Vue 3 é a versão principal atual, mais recente da Vue. Ela contém novos recursos que não estão na Vue 2, como Teleport, Suspense, and múltiplos elementos root por template. Ela também tem mudanças importantes que a tornam imcompatível com a Vue2. Os Detalhes completos estão documentados no [Guia da migração para a Vue 3](https://v3-migration.vuejs.org/).

Apesar das diferenças, a maioria das APIs da Vue são compartilhadas entre as duas principais versões, então a maioria do seu conhecimento da Vue 2 vai continuar a funcionar na Vue 2. Notavelmente, a API de Composição era originalmente um recurso da Vue 3 apenas, mas agora foi portada para a Vue 2 e está disponível na [Vue 2.7](https://github.com/vuejs/vue/blob/main/CHANGELOG.md#270-2022-07-01).

Em geral, a Vue 3 fornece tamanhos de pacotes menores, melhor desempenho, melhor escalabilidade, e um maior suporte a IDEs e TypeScript. Se tu estás a iniciar um novo projeto hoje, a Vue 3 é a escolha recomendada. Existem apenas algumas razões para tu considerar a Vue 2 atualmente:

- Tu precisas dar suporte à IE11. A Vue 3 faz uso de recursos modernos de JavaScript e não oferece suporte à IE11.

- tu estás esperando os principais projetos de ecossistema, como Nuxt ou Vuetify, lançarem versões estáveis para a Vue 3. Isso é razoável se tu não desejas fazer uso de software em estágio beta. Porém, note que existem outras bibliotecas de componentes para a Vue 3 já estáveis, como [Quasar](https://quasar.dev/), [Naive UI](https://www.naiveui.com/) e [Element Plus](https://element-plus.org/).

Se tu pretendes migrar uma aplicação existente da Vue 2 para a Vue 3, consulte o [guia de migração](https://v3-migration.vuejs.org/).

## Is Vue 2 Still Supported? {#is-vue-2-still-supported}

Vue 2.7, which was shipped in July 2022, is the final minor release of the Vue 2 version range. Vue 2 has now entered maintenance mode: it will no longer ship new features, but will continue to receive critical bug fixes and security updates for 18 months starting from the 2.7 release date. This means **Vue 2 will reach End of Life on December 31st, 2023**.

We believe this should provide plenty of time for most of the ecosystem to migrate over to Vue 3. However, we also understand that there could be teams or projects that cannot upgrade by this timeline while still needing to fulfill security and compliance requirements. We are partnering with industry experts to provide extended support for Vue 2 for teams with such needs - if your team expects to be using Vue 2 beyond the end of 2023, make sure to plan ahead and learn more about [Vue 2 Extended LTS](https://v2.vuejs.org/lts/).

## What license does Vue use? {#what-license-does-vue-use}

Vue is a free and open source project released under the [MIT License](https://opensource.org/licenses/MIT).

## What browsers does Vue support? {#what-browsers-does-vue-support}

The latest version of Vue (3.x) only supports [browsers with native ES2015 support](https://caniuse.com/es6). This excludes IE11. Vue 3.x uses ES2015 features that cannot be polyfilled in legacy browsers, so if you need to support legacy browsers, you will need to use Vue 2.x instead.

## Is Vue reliable? {#is-vue-reliable}

Vue is a mature and battle-tested framework. It is one of the most widely used JavaScript frameworks in production today, with over 1.5 million users worldwide, and is downloaded close to 10 million times a month on npm.

Vue is used in production by renowned organizations in varying capacities all around the world, including Wikimedia Foundation, NASA, Apple, Google, Microsoft, GitLab, Zoom, Tencent, Weibo, Bilibili, Kuaishou, and many more.

## Is Vue fast? {#is-vue-fast}

Vue 3 is one of the most performant mainstream frontend frameworks, and handles most web application use cases with ease, without the need for manual optimizations.

In stress-testing scenarios, Vue outperforms React and Angular by a decent margin in the [js-framework-benchmark](https://rawgit.com/krausest/js-framework-benchmark/master/webdriver-ts-results/table.html). It also goes neck-and-neck against some of the fastest production-level non-Virtual-DOM frameworks in the benchmark.

Do note that synthetic benchmarks like the above focus on raw rendering performance with dedicated optimizations and may not be fully representative of real-world performance results. If you care more about page load performance, you are welcome to audit this very website using [WebPageTest](https://www.webpagetest.org/lighthouse) or [PageSpeed Insights](https://pagespeed.web.dev/). This website is powered by Vue itself, with SSG pre-rendering, full page hydration and SPA client-side navigation. It scores 100 in performance on an emulated Moto G4 with 4x CPU throttling over slow 4G networks.

You can learn more about how Vue automatically optimizes runtime performance in the [Rendering Mechanism](/guide/extras/rendering-mechanism) section, and how to optimize a Vue app in particularly demanding cases in the [Performance Optimization Guide](/guide/best-practices/performance).

## Is Vue lightweight? {#is-vue-lightweight}

When you use a build tool, many of Vue's APIs are ["tree-shakable"](https://developer.mozilla.org/en-US/docs/Glossary/Tree_shaking). For example, if you don't use the built-in `<Transition>` component, it won't be included in the final production bundle.

A hello world Vue app that only uses the absolutely minimal APIs has a baseline size of only around **16kb**, with minification and brotli compression. The actual size of the application will depend on how many optional features you use from the framework. In the unlikely case where an app uses every single feature that Vue provides, the total runtime size is around **27kb**.

When using Vue without a build tool, we not only lose tree-shaking, but also have to ship the template compiler to the browser. This bloats up the size to around **41kb**. Therefore, if you are using Vue primarily for progressive enhancement without a build step, consider using [petite-vue](https://github.com/vuejs/petite-vue) (only **6kb**) instead.

Some frameworks, such as Svelte, use a compilation strategy that produces extremely lightweight output in single-component scenarios. However, [our research](https://github.com/yyx990803/vue-svelte-size-analysis) shows that the size difference heavily depends on the number of components in the application. While Vue has a heavier baseline size, it generates less code per component. In real-world scenarios, a Vue app may very well end up being lighter.

## Does Vue scale? {#does-vue-scale}

Yes. Despite a common misconception that Vue is only suitable for simple use cases, Vue is perfectly capable of handling large scale applications:

- [Single-File Components](/guide/scaling-up/sfc) provide a modularized development model that allows different parts of an application to be developed in isolation.

- [Composition API](/guide/reusability/composables) provides first-class TypeScript integration and enables clean patterns for organizing, extracting and reusing complex logic.

- [Comprehensive tooling support](/guide/scaling-up/tooling) ensures a smooth development experience as the application grows.

- Lower barrier to entry and excellent documentation translate to lower onboarding and training costs for new developers.

## How do I contribute to Vue? {#how-do-i-contribute-to-vue}

We appreciate your interest! Please check out our [Community Guide](/about/community-guide).

## Should I use Options API or Composition API? {#should-i-use-options-api-or-composition-api}

If you are new to Vue, we provide a high-level comparison between the two styles [here](/guide/introduction#which-to-choose).

If you have previously used Options API and are currently evaluating Composition API, check out [this FAQ](/guide/extras/composition-api-faq).

## Should I use JavaScript or TypeScript with Vue? {#should-i-use-javascript-or-typescript-with-vue}

While Vue itself is implemented in TypeScript and provides first-class TypeScript support, it does not enforce an opinion on whether you should use TypeScript as a user.

TypeScript support is an important consideration when new features are added to Vue. APIs that are designed with TypeScript in mind are typically easier for IDEs and linters to understand, even if you aren't using TypeScript yourself. Everybody wins. Vue APIs are also designed to work the same way in both JavaScript and TypeScript as much as possible.

Adopting TypeScript involves a trade-off between onboarding complexity and long-term maintainability gains. Whether such a trade-off can be justified can vary depending on your team's background and project scale, but Vue isn't really an influencing factor in making that decision.

## How does Vue compare to Web Components? {#how-does-vue-compare-to-web-components}

Vue was created before Web Components were natively available, and some aspects of Vue's design (e.g. slots) were inspired by the Web Components model.

The Web Components specs are relatively low-level, as they are centered around defining custom elements. As a framework, Vue addresses additional higher-level concerns such as efficient DOM rendering, reactive state management, tooling, client-side routing, and server-side rendering.

Vue also fully supports consuming or exporting to native custom elements - check out the [Vue and Web Components Guide](/guide/extras/web-components) for more details.

<!-- ## TODO How does Vue compare to React? -->

<!-- ## TODO How does Vue compare to Angular? -->
