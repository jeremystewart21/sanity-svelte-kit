<script>
  import {PortableText} from '@portabletext/svelte'
  import Code from '$lib/Code.svelte'
  import Link from '$lib/Link.svelte'
  import ImageBlock from '$lib/ImageBlock.svelte'
  import AuthorBlock from '$lib/AuthorBlock.svelte'
  import AuthorCard from '$lib/AuthorCard.svelte'
  import SanityImage from '$lib/SanityImage.svelte'
  import Saos from 'saos'

  export let post
</script>

<svelte:head>
  <title>{post.title}</title>
</svelte:head>

<Saos animation={'slide-in 0.5s cubic-bezier(0.250, 0.460, 0.450, 0.940) both'}>
  <h1 class="text-4xl font-bold">{post.title}</h1>
  <p class="my-4">
    Published {new Date(post.publishedAt).toLocaleDateString('en', {
      month: 'long',
      day: '2-digit',
      year: 'numeric'
    })}
  </p>
</Saos>

<Saos animation={'slide-in 0.5s cubic-bezier(0.250, 0.460, 0.450, 0.940) both'}>
  <SanityImage image={post.image} />
</Saos>
<div class="mt-20">
  {#if post.image}
    <SanityImage image={post.image} />
  {/if}
</div>

<div class="mt-20">
  <PortableText
    value={post.body}
    components={{
      types: {
        code: Code,
        image: ImageBlock,
        authorReference: AuthorBlock
      },
      marks: {
        link: Link
      }
    }}
  />
</div>

<div class="mt-20 border-t">
  {#each post.authors || [] as author}
    <AuthorCard {author} />
  {/each}
</div>

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
