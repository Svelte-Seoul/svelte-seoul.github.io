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
    <link href={`${origin}/${permalink}`} rel="canonical" />
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
