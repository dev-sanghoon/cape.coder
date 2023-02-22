<script>
  export let log;
  export let helpers;
</script>

<style>
  .feed-title-container {
    display: flex;
    color: #5c3f4f;
  }
  .feed-title {
    padding-left: 5px;
    color: #dbbc7f;
  }
</style>

<div class="feed-title-container">
  <div>[{log.frontmatter.slug}]</div>
  <a class="feed-title" href={helpers.permalinks.articles({ slug: `logs/${log.slug}` })}>{log.frontmatter.question}</a>
</div>
