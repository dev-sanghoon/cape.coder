<script>
  import BlogTeaser from '../../components/BlogTeaser.svelte';

  export let data, helpers;
</script>

<style>
  .feeds {
    padding-left: 0px;
  }
</style>

<ul class="feeds">
  {#each data.markdown.blog as blog}
    <BlogTeaser {blog} {helpers} />
  {/each}
</ul>
