<script>
  import Header from '$lib/Header.svelte'
  import Footer from '$lib/Footer.svelte'
  import '../app.css'
</script>

<Header blogTitle={'SvelteKit x Sanity Blog'} />

<main class="max-w-screen-lg mx-auto">
  <slot />
</main>

<Footer />
