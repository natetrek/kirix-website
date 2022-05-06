<template>

    <!-- Hero area -->
    <div class="flex justify-center mt-20 pb-20"><img src="../assets/logo.png" alt="Kirix logo" /></div>
    <div class="container-inner prose mx-2 md:mx-auto space-y-8">
      <div class="text-3xl md:text-4xl font-bold text-gray-600 text-center">Welcome to Kirix Strata</div>
      <div class="text-xl md:text-2xl text-gray-600 text-center">Open source application for data preparation and ad hoc data analysis</div>
      <div class="flex flex-row justify-center py-8">
          <button class="cta-btn mx-2 text-white bg-orange-500 hover:bg-orange-400" @click="downloadProduct">Download</button>
          <button class="cta-btn mx-2 text-orange-500 hover:text-white hover:bg-orange-400">Get Started</button>
      </div>
    </div>

    <!-- Section 1 -->
    <div class="container-inner prose mx-2 md:mx-auto mb-10">
      <div v-if="isMobile" class="border-t-2 border-gray-100 pb-2"></div>
      <div class="flex flex-col md:flex-row basis-1/3 mx-2 md:mx-auto gap-8 md:gap-12 my-4">
        <div class="flex-col space-y-4">
          <img src="../assets/nature-people.svg" alt="Heading icon 01" width="48px" class="mx-auto">
          <div class="font-semibold text-lg">Feature 1</div>
          <div class="leading-7">Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempora quod fugiat ex delectus neque maxime labore? Exercitationem quidem, beatae omnis illo nobis quos quod accusamus laboriosam modi aliquam quia animi voluptas quibusdam magnam ea?</div>
          <button class="font-bold text-blue-500">Learn More</button>
        </div>
        <div v-if="isMobile" class="border-t-2 border-gray-100"></div>
        <div class="flex-col space-y-4">
          <img src="../assets/task-complete.svg" alt="Heading icon 02" width="48px" class="mx-auto">
          <div class="font-semibold text-lg">Feature 2</div>
          <div class="leading-7">Lorem ipsum dolor sit amet consectetur adipisicing elit. Mollitia aut ratione vitae perferendis est, reprehenderit dolore, minima, error a ea necessitatibus quisquam voluptate magni consequuntur voluptatum tenetur aperiam tempora animi!</div>
          <button class="font-bold text-blue-500">Learn More</button>
        </div>
        <div v-if="isMobile" class="border-t-2 border-gray-100"></div>
        <div class="flex-col space-y-4">
          <img src="../assets/auto-stories.svg" alt="Heading icon 03" width="48px" class="mx-auto">
          <div class="font-semibold text-lg">Feature 3</div>
          <div class="leading-7">Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis saepe nobis quam exercitationem provident eos amet iure, nostrum hic doloremque delectus obcaecati deserunt, sit earum ipsum dolores sequi perspiciatis nesciunt?</div>
          <button class="font-bold text-blue-500">Learn More</button>
        </div>
      </div>
    </div>

    <!-- Visit repository -->
    <div class="visit-repo">
      <div class="container-inner mx-2 md:mx-auto py-16">
        <div class="flex-col text-center text-white space-y-8 md:px-32">
          <div class="text-2xl md:text-3xl">Visit Kirix on GitHub</div>
          <div class="text-left md:text-center leading-7 pb-4">Lorem ipsum dolor sit amet consectetur adipisicing elit. Harum sit enim iure quasi officiis eveniet distinctio natus aliquid corrupti fuga libero impedit officia quis sint ad amet temporibus, incidunt autem!</div>
          <button class="visit-repo-btn" @click="gotoGitHubRepo">Go to repo</button>
        </div>
      </div>
    </div>

</template>

<script>

export default {
  name: "BaseHome",

  data: function() {
    return {
      isMobile: false    };
  },

  created() {
    // add an event listener to the window so we can switch image sizes
    window.addEventListener('resize', this.handleResize)
    this.handleResize()
  },

  destroyed() {
      window.removeEventListener('resize', this.handleResize)
  },

  methods: {
    // update variable used to select mobile display elements
    handleResize() {
      this.isMobile = window.innerWidth < 650;
    },
    downloadProduct() {
      window.open("https://www.kirix.com/assets/downloads.kirix.com/kirix-strata-4.5.4.msi");
    },
    gotoGitHubRepo() {
      window.open("https://github.com/kirixresearch?tab=repositories");
    },
  }
};
</script>

<style scoped>
  .cta-btn {
    text-transform: uppercase;
    font-weight: bold;
    padding: 12px 32px 12px 32px;
    border: 1px solid theme('colors.orange.500');
    border-radius: 5px;
  }

  .visit-repo {
    background-color: #333;
  }
  .visit-repo-btn {
    text-transform: uppercase;
    font-weight: bold;
    padding: 12px 32px 12px 32px;
    background-color: theme('colors.gray.500');
    border: 1px solid theme('colors.gray.500');
    border-radius: 5px;
  }
  .visit-repo-btn:hover {
    border: 1px solid theme('colors.white');
  }

</style>

