<script>
  import SanityImage from './SanityImage.svelte'

  export let post
</script>

<article>
  <a class="" rel="prefetch" href="/blog/{post.slug.current}">
    {#if post.image}
      <div class="">
        <SanityImage image={post.image} maxWidth={300} />
      </div>
    {/if}
    <h2 class="mt-4 font-semibold">
      {post.title}
    </h2>
  </a>
</article>
