<script>
  import SanityImage from './SanityImage.svelte'

  export let author
</script>

{#if author?.name}
  <a href="/authors/{author.slug.current}">
    <span>
      <SanityImage image={author.image} maxWidth={100} />
    </span>
    {author.name}
  </a>
{/if}
