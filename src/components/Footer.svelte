<script lang="ts">
  // make dynamic date to be added to footer
  export let name: string;
  let date = new Date().getFullYear();
</script>

<!-- Remove the container if you want to extend the Footer to full width. -->
<div class="container-fluid m-0 p-0 mt-4">
  <!-- Footer -->
  <footer class="text-center text-lg-start text-white" style="background-color: #1c2331">
    <!-- Section: Social media -->
    <section class="d-flex justify-content-between p-4" style="background-color: #6351ce">
      <!-- Left -->
      <div class="me-5">
        <span>Get connected on social networks:</span>
      </div>
      <!-- Left -->

      <!-- Right -->
      <div>
        <a href="https://www.facebook.com" class="text-white me-4">
          <i class="fab fa-facebook-f" />
        </a>
        <a href="https://twitter.com" class="text-white me-4">
          <i class="fab fa-twitter" />
        </a>
        <a href="https://google.com" class="text-white me-4">
          <i class="fab fa-google" />
        </a>
        <a href="https://instagram.com" class="text-white me-4">
          <i class="fab fa-instagram" />
        </a>
        <a href="https://linkedin.com" class="text-white me-4">
          <i class="fab fa-linkedin" />
        </a>
      </div>
      <!-- Right -->
    </section>
    <!-- Section: Social media -->

    <!-- Copyright -->
    <div class="text-center p-3" style="background-color: rgba(0, 0, 0, 0.2)">
      © {date} Copyright:
      <a class="text-white" href="https://mdbootstrap.com/">{name}</a>
    </div>
    <!-- Copyright -->
  </footer>
  <!-- Footer -->
</div>
<!-- End of .container -->
