<script>
  export let article;
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
  .feed-summary {
    margin-top: 5px;
  }
</style>

<div>
  <div class="feed-title-container">
    <div>{article.frontmatter.date}</div>
    <a class="feed-title" href={helpers.permalinks.articles({ slug: article.slug })}>{article.frontmatter.title}</a>
  </div>
  <p class="feed-summary">{article.frontmatter.excerpt}</p>
</div>
