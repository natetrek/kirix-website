<template>
  <footer class="footer-container text-center bg-neutral-800 py-8 lg:px-4">
      <div class="footer-text">MIT Licensed | Copyright &copy; {{ new Date().getFullYear() }} Nate Williams, Aaron Williams, Ken Kaczmarek, Ben Williams, Dave Williams</div>
  </footer>
</template>

<script>
export default {
  name: "AppFooter",

  data: () => ({
  }),
};
</script>

<style scoped>
  .footer-text {
    font-size: 14px;
    color: #999;
  }

</style>
