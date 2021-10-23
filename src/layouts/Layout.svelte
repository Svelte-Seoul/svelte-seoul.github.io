<script>
  import {ThemeProvider} from 'svelte-theme-provider'

  import Content from './Content.svelte'
</script>

<ThemeProvider initialTheme='dark'>
  <Content {...$$props}/>
</ThemeProvider>
