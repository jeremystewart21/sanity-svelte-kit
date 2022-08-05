<script>
  import AuthorCard from '$lib/AuthorCard.svelte'
  import PostsGrid from '$lib/PostsGrid.svelte'
  import Saos from "saos";

  export let posts
  export let authors
</script>

<svelte:head>
  <title>Blog</title>
</svelte:head>

<Saos animation={"from-left 4s cubic-bezier(0.35, 0.5, 0.65, 0.95) both"}>
  <h1 class="text-sm font-bold">Recent posts small</h1>
</Saos>


<PostsGrid {posts} />

<h2>Author{authors.length > 1 ? 's' : ''}</h2>

{#each authors as author}
  <AuthorCard {author} />
{/each}


<style>
  @keyframes -global-from-left {
  0% {
    transform: rotateX(50deg) translateX(-200vw) skewX(-50deg);
    opacity: 1;
  }
  100% {
    transform: rotateX(0deg) translateX(0) skewX(0deg);
    opacity: 1;
  }
}
</style>