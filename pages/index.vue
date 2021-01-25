<template>
  <div
    class="min-h-screen pt-10 w-10/12 m-auto h-screen flex flex-col justify-between max-w-3xl"
  >
    <div>
      <header>
        <h1 class="text-5xl uppercase font-bold text-center text-red-600">
          {{ name }}
        </h1>
        <p
          class="text-center text-lg w-10/12 text-center m-auto mt-8 mb-3 max-w-md"
        >
          {{ description }}
        </p>
        <span class="w-3/12 h-1 block m-auto rounded-full bg-red-600"></span>

        <div class="mt-3">
          <ul class="flex justify-center p-2">
            <li v-for="(social, index) in contact" :key="index" class="mr-4">
              <a :href="social.url" v-html="social.icon" target="_blank" />
            </li>
          </ul>
        </div>
      </header>

      <main class="my-12">
        <p class="text-lg">
          {{ introduction }}
        </p>

        <section class="mt-12">
          <h2 class="font-bold my-4 text-xl text-red-600">
            Some Of My Projects ...
          </h2>
          <ul
            class="text-lg grid grid-cols-1 gap-x-3 sm:grid-cols-2 md:grid-cols-3"
          >
            <li
              v-for="(project, index) in projects"
              :key="index"
              class="mb-6 p-4 rounded bg-gray-100 flex flex-col justify-between"
            >
              <div>
                <p class="font-semibold text-red-600">{{ project.title }}</p>
                <p class="mt-2">{{ project.description }}</p>
              </div>
              <div class="flex justify-between mt-6">
                <a
                  :href="project.source"
                  class="bg-transparent py-1 px-4 rounded text-red-600 border border-red-600"
                  target="_blank"
                  >Source</a
                >
                <a
                  :href="project.link"
                  class="bg-red-600 py-1 px-4 rounded text-white font-semibold"
                  target="_blank"
                  >View</a
                >
              </div>
            </li>
          </ul>
        </section>
      </main>
    </div>

    <footer class="py-5 text-center">
      <p>Made with ❤️ by Oriane Louis</p>
      <p>© 2021, Built with NuxtJS</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      name: 'Oriane Louis',
      description:
        'I like writing code to build things and improve user experience with JavaScript, VueJS, ReactJS, NodeJs',
      contact: [
        {
          icon:
            '<svg width="24" height="24" role="img" viewBox="0 0 24 24" fill="#dc2626" color="#000000" xmlns="http://www.w3.org/2000/svg"><title>LinkedIn icon</title><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"></path></svg>',
          url: 'https://www.linkedin.com/in/oriane-louis/',
        },
        {
          icon:
            '<svg width="30px" height="30px" role="img" viewBox="0 0 24 24" fill="#dc2626" color="#000000" xmlns="http://www.w3.org/2000/svg"><title>GitHub icon</title><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"></path></svg>',
          url: 'https://github.com/o-louis',
        },
        {
          icon:
            '<svg width="30px" height="30px" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#dc2626" color="#000000"><title>CodePen icon</title><path d="M18.144 13.067v-2.134L16.55 12zm1.276 1.194a.628.628 0 01-.006.083l-.005.028-.011.053-.01.031c-.005.016-.01.031-.017.047l-.014.03a.78.78 0 01-.021.043l-.019.03a.57.57 0 01-.08.1l-.026.025a.602.602 0 01-.036.03l-.029.022-.01.008-6.782 4.522a.637.637 0 01-.708 0L4.864 14.79l-.01-.008a.599.599 0 01-.065-.052l-.026-.025-.032-.034-.021-.028a.588.588 0 01-.067-.11l-.014-.031a.644.644 0 01-.017-.047l-.01-.03c-.004-.018-.008-.036-.01-.054l-.006-.028a.628.628 0 01-.006-.083V9.739c0-.028.002-.055.006-.083l.005-.027.011-.054.01-.03a.574.574 0 01.12-.217l.031-.034.026-.025a.62.62 0 01.065-.052l.01-.008 6.782-4.521a.638.638 0 01.708 0l6.782 4.521.01.008.03.022.035.03c.01.008.017.016.026.025a.545.545 0 01.08.1l.019.03a.633.633 0 01.021.043l.014.03c.007.016.012.032.017.047l.01.031c.004.018.008.036.01.054l.006.027a.619.619 0 01.006.083zM12 0C5.373 0 0 5.372 0 12 0 18.627 5.373 24 12 24c6.628 0 12-5.372 12-12 0-6.627-5.372-12-12-12m0 10.492L9.745 12 12 13.51 14.255 12zm.638 4.124v2.975l4.996-3.33-2.232-1.493zm-6.272-.356l4.996 3.33v-2.974l-2.764-1.849zm11.268-4.52l-4.996-3.33v2.974l2.764 1.85zm-6.272-.356V6.41L6.366 9.74l2.232 1.493zm-5.506 1.549v2.134L7.45 12Z"></path></svg>',
          url: 'https://codepen.io/reavenclaw',
        },
        {
          icon:
            '<svg width="30px" height="30px" role="img" viewBox="0 0 24 24" fill="#dc2626" color="#000000" xmlns="http://www.w3.org/2000/svg"><title>Gmail icon</title><path d="M24 4.5v15c0 .85-.65 1.5-1.5 1.5H21V7.387l-9 6.463-9-6.463V21H1.5C.649 21 0 20.35 0 19.5v-15c0-.425.162-.8.431-1.068C.7 3.16 1.076 3 1.5 3H2l10 7.25L22 3h.5c.425 0 .8.162 1.069.432.27.268.431.643.431 1.068z"></path></svg>',
          url: 'oriane.louis.pro@gmail.com',
        },
      ],
      introduction:
        'Passionate developer specialized in front-end development and enthusiast about new technologies. I have worked on real life projects and find myself capable enough to handle pressure well. I keep learning everyday because web development is moving fast !',
      projects: [
        {
          title: 'CodeTips',
          description: 'Gathers a list of JavaScript Fundamentals',
          link: 'https://code-tips.netlify.app/',
          source: 'https://github.com/o-louis/CodeTips',
        },
        {
          title: 'VueFlix',
          description: 'Search and consult Movie details',
          link: 'https://vueflixx.netlify.app/',
          source: 'https://github.com/o-louis/movie-vuejs2',
        },
        {
          title: 'CovidTracker',
          description: 'Tracker of the Covid-19',
          link: 'https://covid-trackerv2.netlify.app/',
          source: 'https://github.com/o-louis/covid-tracker-v2',
        },
      ],
    }
  },
}
</script>

<style>
* {
  box-sizing: border-box;
}

svg {
  width: 30px;
  height: 30px;
}

li:last-child {
  margin-right: 0px !important;
}
</style>
