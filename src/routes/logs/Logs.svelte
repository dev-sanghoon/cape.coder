<script>
  export let data, request, settings; // data is mainly being populated from the @elderjs/plugin-markdown
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
    /* background: #384b55; */
    background: #1e2326;
    padding: 1rem;
    border-radius: 1rem;
  }

  :global(blockquote) {
    font-weight: bold;
  }

  /* :global(blockquote) {
    margin: 0;
    background: #384b55;
    padding: 3px 1.5rem 3px 3rem;
    position: relative;
    border-radius: 1rem;
  } */

  /* :global(blockquote:after) {
    content: '>';
    color: #aaa;
    font-size: 30px;
    position: absolute;
    top: 23%;
    left: 1rem;
  } */

  /* :global(blockquote p) {
    padding: 0;
  } */
</style>

<svelte:head>
  <title>{frontmatter.question}</title>
  <meta name="description" content={frontmatter.question} />
  <link href="{settings.origin}{request.permalink}" rel="canonical" />
</svelte:head>

<div class="title">
  <h2>{frontmatter.question}</h2>
  <!-- {#if frontmatter.author}<small>By {frontmatter.author}</small>{/if} -->
</div>

{#if html}
  {@html html}
{:else}
  <h1>Oops!! Markdown not found!</h1>
{/if}
