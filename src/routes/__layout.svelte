<script>
  import Header from '$lib/Header.svelte'
  import Footer from '$lib/Footer.svelte'
  import '../app.css'
</script>

<Header blogTitle={'Jeremy Sanity and Svelte Test'} />

<main class="">
  <slot />
</main>

<Footer />
