<script setup>
import AboutMe from "./components/body/AboutMe.vue";
import Experience from "./components/body/Experience.vue";
import Introduction from "./components/body/Introduction.vue";
import Projects from "./components/body/Projects.vue";
import Footer from "./components/footer/Footer.vue";
import Header from "./components/header/Header.vue";

const downloadCV = () => {
  const link = document.createElement("a");
  link.href = "/file/Rich-Deshan-Djuardi-Front-End-Developer-Resume-CV.pdf";
  link.download = "Rich Deshan Djuardi - Resume.pdf";
  document.body.appendChild(link);
  link.click();
  document.body.removeChild(link);
};
</script>

<template>
  <div
    class="min-h-screen bg-gradient-to-br from-orange-50 via-white to-orange-200 relative overflow-hidden"
  >
    <div
      class="absolute inset-0 opacity-[0.25] pointer-events-none"
      style="
        background-image: url('https://grainy-gradients.vercel.app/noise.svg');
        mix-blend-mode: soft-light;
      "
    ></div>

    <div class="relative z-10 w-full">
      <header
        class="w-full border-b border-orange-100/70 py-2 px-4 sm:px-6 md:px-10 lg:px-20 xl:px-32 backdrop-blur-md bg-white/40"
      >
        <h1>
          <Header />
        </h1>
      </header>

      <main
        class="mx-auto py-2 px-4 sm:px-6 md:px-10 lg:px-20 xl:px-32 max-w-6xl"
      >
        <div class="flex flex-col gap-4">
          <div>
            <section id="home">
              <Introduction />
            </section>

            <section id="about">
              <AboutMe />
            </section>

            <section id="experiences">
              <Experience />
            </section>

            <section id="projects">
              <Projects />
            </section>

            <section id="contacts">
              <footer></footer>
            </section>
          </div>
        </div>
      </main>

      <footer
        class="w-full border-t border-orange-100/70 bg-white/50 backdrop-blur-md"
      >
        <Footer />
      </footer>
    </div>
  </div>
  <button
    @click="downloadCV"
    class="fixed bottom-5 right-5 z-50 flex items-center gap-2 rounded-full bg-orange-500 text-white px-4 py-3 text-sm font-semibold shadow-lg shadow-orange-300/40 active:scale-95 transition md:hidden"
  >
    Download CV
  </button>
</template>
