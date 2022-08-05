<script context="module">
  import {page} from '$app/stores'
</script>

<script>
  export let blogTitle = 'My Blog'

  let path
  $: ({pathname} = $page)
</script>

<header class="max-w-screen-lg mx-auto py-8">
  <span>{blogTitle}</span>
  <nav>
    <ul>
      <li><a data-selected={pathname === '/'} href="/">home</a></li>
    </ul>
  </nav>
</header>
