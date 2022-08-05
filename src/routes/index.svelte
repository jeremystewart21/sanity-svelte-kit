<script>
  import AuthorCard from '$lib/AuthorCard.svelte'
  import PostsGrid from '$lib/PostsGrid.svelte'
  import Saos from 'saos'

  export let posts
  export let authors
</script>

<svelte:head>
  <title>Blog</title>
</svelte:head>

<section class="bg-gray-800 w-full">
  <div class="flex items-center h-[650px]">
    <div class="pl-6 md:pl-24 lg:pl-40 xl:pl-48 pr-32 w-2/3">
      <Saos once={true} animation={'from-left 1s cubic-bezier(0.35, 0.5, 0.65, 0.95) both'}>
        <h1 class="text-white">Why Bestrane</h1>
        <p class="text-5xl text-orange mt-4">
          Discover why leading businesses trust Bestrane to solve their complex logistics problems.
        </p>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          class="h-6 w-6 text-orange mt-8 heroanim4 invisible"
          style="opacity: 1; visibility: inherit;"
          ><path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M19 14l-7 7m0 0l-7-7m7 7V3"
          /></svg
        >
      </Saos>
    </div>
    <div class="h-full w-1/3">
      <Saos once={true} animation={'from-right 1s cubic-bezier(0.35, 0.5, 0.65, 0.95) 0.3s both'}>
        <img
          class="h-[650px] object-cover"
          src="https://cdn.sanity.io/images/njsn8sgm/production/47444df23d32a18e030c9f1875c23697e2290a2b-5953x3969.jpg?w=751&h=630&auto=format"
          alt=""
        />
      </Saos>
    </div>
  </div>
</section>

<h1 class="text-sm font-bold mb-20">Recent posts small</h1>

<div class="max-w-screen-md mx-auto">
  <PostsGrid {posts} />
</div>

<h2>Author{authors.length > 1 ? 's' : ''}</h2>

{#each authors as author}
  <AuthorCard {author} />
{/each}

<style>
  @keyframes -global-from-right {
    0% {
      transform: translateX(100px);
      opacity: 0;
    }
    100% {
      transform: translateX(-0px);
      opacity: 1;
    }
  }
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
