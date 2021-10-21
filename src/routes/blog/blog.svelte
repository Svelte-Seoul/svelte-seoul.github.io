<script>
    export let data, request, settings;
    
     const { html, frontmatter : { title, summary }, tocTree } = data;

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
    {#if html}
        {@html html}
    {:else}
        <h1>Markdown not found!</h1>
    {/if}
</article>
