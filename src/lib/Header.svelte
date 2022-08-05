<script context="module">
  import {page} from '$app/stores'
</script>

<script>
  export let blogTitle = 'My Blog'

  let path
  $: ({pathname} = $page)
</script>

<header class="max-w-screen-lg mx-auto py-8 flex justify-between">
  <nav>
    <ul>
      <li><a data-selected={pathname === '/'} href="/">home</a></li>
    </ul>
  </nav>
  <span class="font-bold">{blogTitle}</span>
</header>
