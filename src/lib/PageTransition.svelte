<script>
  import {fly} from 'svelte/transition'
  export let url = ''
</script>

{#key url}
  <div in:fly={{y: 0, duration: 200, delay: 300}} out:fly={{y: 0, duration: 200, delay: 300}}>
    <slot />
  </div>
{/key}
