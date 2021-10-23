<script>
    import TableOfContent from '../../components/TableOfContent.svelte'

    export let data, request, settings;
    
    const { html, frontmatter : { title, summary, toc, author }, tocTree } = data;

    const [name, profile] = author.split(/[()]/);
    
    const { permalink } = request;
    
    const { origin } = settings;
</script>

<style>
    span {
        display: flex;
        flex-direction: row;
        align-items: center;
    }

    a {
        font-size: 12px;
        margin-left: 10px;
    }
</style>

<svelte:head>
    <title>{title}</title>
    <meta name="description" content={summary} />
    <link href={`${origin}${permalink}`} rel="canonical" />

    <meta property="og:site_name" content="Svelte Seoul | 스벨트 서울">
    <meta property="og:url" content={`${origin}${permalink}`}>
    <meta property="og:title" content={title}>
    <!-- <meta property="og:image" content=""> -->
    <meta property="og:description" content={summary}>
  
    <meta name="twitter:card" content="summary">
    <meta name="twitter:url" content={`${origin}${permalink}`}>
    <meta name="twitter:title" content={title}>
    <meta name="twitter:description" content={summary}>
    <!-- <meta name="twitter:image" content=""> -->
</svelte:head>

<article>
    <section>
        <span>
            <h1>{title}</h1>
            <a href={profile}>{`by ${name}`}</a>
        </span>
    </section>
    {#if toc}
        <TableOfContent {tocTree}/>
    {/if}
    {#if html}
        {@html html}
    {:else}
        <h1>Markdown not found!</h1>
    {/if}
</article>
