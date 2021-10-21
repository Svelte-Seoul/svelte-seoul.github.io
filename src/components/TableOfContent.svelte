<script>
  export let tocTree;
</script>

{#if tocTree.length !== 0}
  <nav>
    <span>목차</span>
    <ol>
      {#each tocTree as {id, text, children: tocTree}}
        <li>
          <a href={`#${id}`}>
            {text}
          </a>
          {#if tocTree.length !== 0}
            <ol>
              {#each tocTree as {id, text}}
                <li>
                  <a href={`#${id}`}>
                    {text}
                  </a>
                </li>
              {/each}
            </ol>
          {/if}
        </li>
      {/each}
    </ol>
  </nav>
{/if}
  