<script>
  import MailAddress from '../../components/MailAddress.svelte';
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

<ul>
  <MailAddress hydrate-client={{}} />
  <div>
    <a class="info-item" href="https://github.com/dev-sanghoon" target="_blank" rel="noreferrer">
      github.com/dev-sanghoon
    </a>
  </div>
</ul>
