<script>
  import Header from '$lib/Header.svelte'
  import Footer from '$lib/Footer.svelte'
  import '../app.css'
</script>

<Header blogTitle={'Jeremy Sanity and Svelte Test'} />

<main class="max-w-screen-lg mx-auto">
  <slot />
</main>

<Footer />
