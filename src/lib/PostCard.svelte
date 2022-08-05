<script>
  import SanityImage from './SanityImage.svelte'
  import Saos from 'saos'

  export let post
</script>

<article>
  <a class="" rel="prefetch" href="/blog/{post.slug.current}">
    {#if post.image}
      <Saos once={true} animation={'slide-in 0.5s cubic-bezier(0.250, 0.460, 0.450, 0.940) both'}>
        <SanityImage image={post.image} />
      </Saos>
    {/if}
    <Saos once={true} animation={'fade-in 2s cubic-bezier(0.35, 0.5, 0.65, 0.95) 1s both'}>
      <h2 class="mt-4 font-semibold text-2xl">
        {post.title}
      </h2>
    </Saos>
  </a>
</article>

<style>
  @keyframes -global-fade-in {
    0% {
      opacity: 0;
    }
    100% {
      opacity: 1;
    }
  }
  @keyframes -global-slide-in {
    0% {
      transform: translateY(300px);
      opacity: 0;
    }
    100% {
      transform: translateY(0);
      opacity: 1;
    }
  }
</style>
