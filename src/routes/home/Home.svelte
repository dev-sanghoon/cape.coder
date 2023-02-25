<script>
  import ArticleTeaser from '../../components/ArticleTeaser.svelte';

  export let data, request, settings, helpers;
</script>

<style>
  .feeds {
    padding-left: 0px;
  }
</style>

<svelte:head>
  <title>Cape.Coder 기술 블로그</title>
  <meta name="description" content="Cape.Coder 기술 블로그" />
  <link href="{settings.origin}{request.permalink}" rel="canonical" />
</svelte:head>

<ul class="feeds">
  {#each data.markdown.articles as article}
    <ArticleTeaser {article} {helpers} />
  {/each}
</ul>
