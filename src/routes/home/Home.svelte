<script>
  import PostCard from '../../components/PostCard.svelte'

  export let data, helpers, settings;

  const posts = data.markdown.blog;
</script>

<style>
  a {
    padding: 4px;
    font-size: 12px;
  }
</style>

<svelte:head>
  <title>Svelte Seoul | 스벨트 서울</title>
  <meta name="description" content="Svelte 스벨트 사용자 커뮤니티" />
  <link href="{settings.origin}/" rel="canonical" />
</svelte:head>

<main class="banner">
  <h1>Svelte Seoul</h1>
  <p>Svelte 사용자 커뮤니티</p>

  <a href="https://github.com/Svelte-Seoul">Github</a>
  <a href="https://medium.com/svelte-seoul">Medium</a>
  <a href="https://join.slack.com/t/svelteseoul/shared_invite/zt-xf8buzpe-xZnJcIWJFHj9fueYZojPNw">Slack</a>
</main>

<PostCard {posts} />
