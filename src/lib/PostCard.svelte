<script>
  import SanityImage from './SanityImage.svelte'
  import Saos from "saos";


  export let post
</script>

<article>
  <a class="" rel="prefetch" href="/blog/{post.slug.current}">
    {#if post.image}

    <Saos animation={"fade-in 2s cubic-bezier(0.35, 0.5, 0.65, 0.95) both"}>
      <SanityImage image={post.image} />
    </Saos>

 
      <!-- <div class="">
        <SanityImage image={post.image} maxWidth={300} />
      </div> -->
    {/if}
    <h2 class="mt-4 font-semibold">
      {post.title}
    </h2>
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
</style>