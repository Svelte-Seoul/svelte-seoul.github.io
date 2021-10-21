<script>
    export let posts;
</script>

<style>
    a {
        padding: 4px;
        font-size: 12px;
        text-decoration: none;
        color:black;
    }

    a:hover {
        color:#ff3e00;
    }
</style>
  
<section class="banner">
    {#if posts.length === 0}
        <p>아직 글이 없습니다.</p>
    {/if}
    
    {#each posts as {slug, frontmatter: {title, summary}} (title)}
        <a href={`/${slug}/`}>
            <div class="card">
                <h2>{title}</h2>
                <h3>{summary}</h3>
            </div>
        </a>
    {/each}
</section>
