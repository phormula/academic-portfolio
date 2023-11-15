<script>
  import Header from './components/Header.svelte';
  import Footer from './components/Footer.svelte';
  import { Container } from 'sveltestrap';
  import profile from './assets/profile-img.jpg';
  import content from './lib/content.json';
</script>

<div class="app">
  <Header name={content.name} />

  <div class="container-fluid p-0">
    <div class="container-fluid p-0">
      <div class="d-flex justify-content-center p-4 bg-dark text-light">
        <h3>{content.name}</h3>
      </div>
    </div>
    <Container>
      <div class="card mb-3 border-0 my-4">
        <div class="row g-0">
          <div class="col-md-4">
            <img src={profile} class="img-fluid rounded-3" alt="profile-img" />
          </div>
          <div class="col-md-8">
            <div class="card-body">
              <h5 class="card-title">About ME</h5>
              <p class="card-text">
                {content.about}
              </p>
              <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>
            </div>
          </div>
        </div>
      </div>
    </Container>

    <div class="container my-4" id="publication">
      <h4>Publications</h4>
      <ul class="publication list-unstyled">
        {#each content.publications as publication}
          <li class="d-flex">{publication}</li>
        {/each}
      </ul>

      <div class="d-flex justify-content-center">
        <a href={content.google_scholar} class="btn-link" target="_blank">
          You can find more up-to-date publications
        </a>
      </div>
    </div>

    <div class="container my-4" id="research">
      <h4>Research Area</h4>
      <ul><li>{content.research_area}</li></ul>
    </div>

    <div class="container my-4" id="software">
      <h4>Software Projects</h4>
      Open source software projects can be found on my
      <a href={content.github_repo} target="_blank"><i class="fa-brands fa-github" /> Github repository</a>
    </div>

    <div class="container my-4" id="contact">
      <h4>Contact</h4>
      <div class="d-flex flex-row">
        <a href="mail:{content.email}" class="me-4">
          <i class="fa-solid fa-envelope fa-2xl" />
        </a>
        <a href="https://www.facebook.com" class="me-4">
          <i class="fab fa-facebook-f fa-2xl" />
        </a>
        <a href="https://twitter.com" class="me-4">
          <i class="fab fa-twitter fa-2xl" />
        </a>
        <a href="https://google.com" class="me-4">
          <i class="fab fa-google fa-2xl" />
        </a>
        <a href="https://instagram.com" class="me-4">
          <i class="fab fa-instagram fa-2xl" />
        </a>
        <a href="https://linkedin.com" class="me-4">
          <i class="fab fa-linkedin fa-2xl" />
        </a>
      </div>
    </div>
  </div>

  <Footer name={content.name} />
</div>

<style>
  .app {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }

  ul.publication li::before {
    display: inline-block;
    height: 100%;
    vertical-align: middle;
    margin-right: 5px;
    content: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24' fill='none'%3E%3Cpath d='M7.75 11.9999L10.58 14.8299L16.25 9.16992' stroke='%2300ADB5' stroke-width='1.5' stroke-linecap='round' stroke-linejoin='round'/%3E%3C/svg%3E");
  }
</style>
