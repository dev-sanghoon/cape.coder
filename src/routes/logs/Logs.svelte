<script>
  export let data, request, settings;
  const { html, frontmatter } = data;
</script>

<style>
  h1 {
    margin-bottom: 10px;
  }

  .title {
    margin-top: 1rem;
    margin-bottom: 1rem;
    padding-bottom: 1rem;
  }

  :global(h2) {
    margin-top: 2rem;
  }

  :global(pre) {
    background: #1e2326;
    padding: 1rem;
    border-radius: 1rem;
  }

  :global(blockquote) {
    font-weight: bold;
  }
</style>

<svelte:head>
  <title>{frontmatter.question}</title>
  <meta name="description" content={frontmatter.question} />
  <link href="{settings.origin}{request.permalink}" rel="canonical" />
</svelte:head>

<div class="title">
  <h2>{frontmatter.question}</h2>
</div>

{#if html}
  {@html html}
{:else}
  <h1>Oops!! Markdown not found!</h1>
{/if}
