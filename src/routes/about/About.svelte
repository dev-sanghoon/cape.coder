<script>
  import MailAddress from '../../components/MailAddress.svelte';

  export let request, settings;
</script>

<style>
  .info-item {
    color: #3a94c5;
    text-decoration-line: none;
    margin-right: 5px;
  }
  .info-item:hover {
    cursor: pointer;
    text-decoration-line: underline;
  }
</style>

<svelte:head>
  <title>소개</title>
  <meta name="description" content="저를 소개합니다" />
  <link href="{settings.origin}{request.permalink}" rel="canonical" />
</svelte:head>

<ul>
  <MailAddress hydrate-client={{}} />
  <div>
    <a class="info-item" href="https://github.com/dev-sanghoon" target="_blank" rel="noreferrer">
      github.com/dev-sanghoon
    </a>
  </div>
</ul>
