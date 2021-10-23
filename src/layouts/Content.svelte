<script>
    import { getContext } from 'svelte';

    import style from '../../assets/style.css'
    
    export let templateHtml, settings, request;
    
    const { permalink } = request;

    const {Theme} = getContext('theme');
    const color = $Theme.theme.danger;
</script>

<style>
    .container {
        font-family: Nanum Gothic Coding;
        max-width: 900px;
        margin: 0 auto;
        padding: 1rem;
    }
</style>

<svelte:head>
    <link rel="stylesheet" href="//fonts.googleapis.com/earlyaccess/nanumgothiccoding.css">
</svelte:head>

<article class="container">
    {#if permalink !== '/'}
        <a href='/'>Back to Home</a>
    {/if}
    {@html templateHtml}
</article>
