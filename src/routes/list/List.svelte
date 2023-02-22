<script>
  import LogTeaser from '../../components/LogTeaser.svelte';

  export let data, helpers;
</script>

<style>
  .feeds {
    padding-left: 0px;
  }
</style>

<ul class="feeds">
  {#each data.markdown.logs as log}
    <LogTeaser {log} {helpers} />
  {/each}
</ul>
