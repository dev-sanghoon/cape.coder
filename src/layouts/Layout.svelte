<script>
  import '../../assets/style.css';

  export let templateHtml;
</script>

<style>
  .header {
    margin-top: 30px;
    display: flex;
    align-items: baseline;
  }
  .title {
    margin-left: 25px;
    margin-right: max(20%, 100px);
    white-space: nowrap;
    color: #e67e80;
    display: block;
    font-size: 1.5em;
    margin-top: 0.83em;
    margin-bottom: 0.83em;
    font-weight: bold;
  }
  .categories {
    display: flex;
  }
  .category-item {
    margin-right: 30px;
    font-weight: bold;
    color: #e69875;
    text-decoration-line: underline;
  }
</style>

<nav class="header">
  <a class="title" href="/">Cape.Coder</a>
  <div class="categories">
    <a class="category-item" href="/logs/">Logs</a>
    <a class="category-item" href="/about/">About</a>
  </div>
</nav>

<div class="container">
  {@html templateHtml}
</div>
