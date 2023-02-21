<script>
  import ArticleTeaser from '../../components/ArticleTeaser.svelte';

  export let data, helpers;
</script>

<style>
  .feeds {
    padding-left: 0px;
  }
</style>

<ul class="feeds">
  {#each data.markdown.articles as article}
    <ArticleTeaser {article} {helpers} />
  {/each}
</ul>
