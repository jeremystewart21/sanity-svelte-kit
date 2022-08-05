<script context="module">
  import {page} from '$app/stores'
</script>

<script>
  export let blogTitle = 'My Blog'

  let path
  $: ({pathname} = $page)
</script>

<header>
  <span>{blogTitle}</span>
  <nav>
    <ul>
      <li><a data-selected={pathname === '/'} href="/">home</a></li>
    </ul>
  </nav>
</header>
