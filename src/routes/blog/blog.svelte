<script>
    import TableOfContent from '../../components/TableOfContent.svelte'

    export let data, request, settings;
    
    const { html, frontmatter : { title, summary, toc }, tocTree } = data;

    console.log(tocTree);
    
    const { permalink } = request;

    const { origin } = settings;
</script>

<svelte:head>
    <title>{title}</title>
    <meta name="description" content={summary} />
    <link href={`${origin}/${permalink}`} rel="canonical" />
</svelte:head>

<article>
    <h1>{title}</h1>
    <TableOfContent {tocTree}/>
    {#if html}
        {@html html}
    {:else}
        <h1>Markdown not found!</h1>
    {/if}
</article>
