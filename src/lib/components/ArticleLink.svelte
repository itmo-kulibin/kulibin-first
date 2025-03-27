<script>
    export let text;
    export let pagename;
  </script>
  
  <a class="article-link" href={`./${pagename}`}>
    <span>{text}</span>
    <span class="arrow">→</span>
  </a>
  
  <style>
    .article-link {
      display: flex;
      justify-content: space-between;
      align-items: center;
      text-decoration: none;
      color: black;
      padding: 12px 16px;
      border-bottom: 1px solid #000;
      font-size: 18px;
    }
  
    .article-link:hover {
      background-color: rgba(0, 0, 0, 0.05);
    }
  
    .arrow {
      font-size: 18px;
    }
  </style>
  