<script>
  import LogTeaser from '../../components/LogTeaser.svelte';

  export let data, request, settings, helpers;
</script>

<style>
  .feeds {
    padding-left: 0px;
  }
</style>

<svelte:head>
  <title>개발 일지</title>
  <meta name="description" content="개발 도중 마주친 기술적인 이슈를 메모하는 일지" />
  <link href="{settings.origin}{request.permalink}" rel="canonical" />
</svelte:head>

<ul class="feeds">
  {#each data.markdown.logs as log}
    <LogTeaser {log} {helpers} />
  {/each}
</ul>
