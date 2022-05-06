<template>

    <!-- Hero area -->
    <div class="flex justify-center mt-20 pb-20"><img src="../assets/logo.png" alt="Kirix logo" /></div>
    <div class="container-inner prose mx-2 md:mx-auto space-y-8 mb-8">
      <div class="text-3xl md:text-4xl font-bold text-gray-600 text-center">Welcome to Kirix Strata</div>
      <div class="text-xl md:text-2xl text-gray-600 text-center">Open source Windows application for data preparation and ad hoc data analysis</div>
      <div class="flex flex-row justify-center py-8">
          <button class="cta-btn mx-2 text-white bg-orange-500 hover:bg-orange-400" @click="downloadProduct">Download</button>
          <button class="cta-btn mx-2 text-orange-500 hover:text-white hover:bg-orange-400">Get Started</button>
      </div>
    </div>

    <!-- Features-1 -->
    <div class="container-inner prose mx-2 md:mx-auto mb-10">
      <div v-if="isMobile" class="border-t-2 border-gray-100 pb-2"></div>
      <div class="flex flex-col md:flex-row basis-1/3 mx-2 md:mx-auto gap-8 md:gap-12 my-4">
        <div class="flex-col space-y-4">
          <img src="../assets/ex_explore_new_data_01.png" alt="Explore new data" class="mx-auto shadow-xl">
          <div class="font-semibold text-lg">Explore Data Sets</div>
          <div class="feature-text">Identify potential problems in a new data set. Correct the issues before your analysis to prevent problems down the road.</div>
          <button class="font-bold text-blue-500">Learn More</button>
        </div>
        <div v-if="isMobile" class="border-t-2 border-gray-100"></div>
        <div class="flex-col space-y-4">
          <img src="../assets/ex_multiple_databases_01.png" alt="Work with multiple databases" class="mx-auto shadow-xl">
          <div class="font-semibold text-lg">Many Databases, One Screen</div>
          <div class="feature-text">Ever want to just drag and drop Oracle tables into SQL Server? Access, manipulate and join data from multiple back-end systems.</div>
          <button class="font-bold text-blue-500">Learn More</button>
        </div>
        <div v-if="isMobile" class="border-t-2 border-gray-100"></div>
        <div class="flex-col space-y-4">
          <img src="../assets/ex_dirty_data_01.png" alt="Clean up dirty data" class="mx-auto shadow-xl">
          <div class="font-semibold text-lg">Clean up Dirty Data</div>
          <div class="feature-text">Got data with incorrect formatting? Need to pull out a piece of data embedded in a field? Quickly clean up your data with dynamic calculations.</div>
          <button class="font-bold text-blue-500">Learn More</button>
        </div>
      </div>
    </div>

    <!-- Features-2 -->
    <div class="container-inner prose mx-2 md:mx-auto mb-16">
      <div v-if="isMobile" class="border-t-2 border-gray-100 pb-2"></div>
      <div class="flex flex-col md:flex-row basis-1/3 mx-2 md:mx-auto gap-8 md:gap-12 my-4">
        <div class="flex-col space-y-4">
          <img src="../assets/ex_millions_of_rows_01.png" alt="Work with millions of rows" class="mx-auto shadow-xl">
          <div class="font-semibold text-lg">Millions of Rows</div>
          <div class="feature-text">There are no 2 GB file size limits or row constraints here. Work with as much data as you have and do it quickly.</div>
          <button class="font-bold text-blue-500">Learn More</button>
        </div>
        <div v-if="isMobile" class="border-t-2 border-gray-100"></div>
        <div class="flex-col space-y-4">
          <img src="../assets/ex_create_reports_01.png" alt="Create ad hoc reports" class="mx-auto shadow-xl">
          <div class="font-semibold text-lg">Ad Hoc Reports</div>
          <div class="feature-text">Create ad hoc reports in minutes. Work with your local data files or create reports directly from Oracle, SQL Server, MySQL, etc.</div>
          <button class="font-bold text-blue-500">Learn More</button>
        </div>
        <div v-if="isMobile" class="border-t-2 border-gray-100"></div>
        <div class="flex-col space-y-4">
          <img src="../assets/ex_csv_tool_01.png" alt="Transform CSV data" class="mx-auto shadow-xl">
          <div class="font-semibold text-lg">Transform CSV Data</div>
          <div class="feature-text">Strata transforms your fixed-length and text-delimited files before your eyes. No wizards needed; open and work with CSV data directly.</div>
          <button class="font-bold text-blue-500">Learn More</button>
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
  }
};
</script>

<style scoped>
  .feature-text {
    line-height: 1.7;
    max-width: 300px;
  }
  .cta-btn {
    text-transform: uppercase;
    font-weight: bold;
    padding: 12px 32px 12px 32px;
    border: 1px solid theme('colors.orange.500');
    border-radius: 5px;
  }

</style>

