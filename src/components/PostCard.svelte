<script>
    export let posts;
</script>

<style>
    a {
        font-size: 10px;
        margin: 10px;
    }

    span {
        display: flex;
        flex-direction: row;
        align-items: center;
    }

    h2 + span {
        margin-left: 10px;
    }
</style>
  
<section class="banner">
    {#if posts.length === 0}
        <p>아직 글이 없습니다.</p>
    {/if}
    
    {#each posts as {slug, frontmatter: {title, summary, date}} (title)}
        <a class="card" href={`/${slug}/`}>
            <span>
                <h2>{title}</h2> 
                <span>{date}</span>
            </span>
            <h3>{summary}</h3>
        </a>
    {/each}
</section>
