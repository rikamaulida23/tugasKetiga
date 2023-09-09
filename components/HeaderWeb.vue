<template>
  <header class="header">
    <nav class="nav">
      <div class="logo">MamaCook</div>
      <ul class="menu">
        <li><a href="/">Beranda</a></li>
        <li><a href="/resep">Contact</a></li>
        <li><a href="/tentang">Tentang Kami</a></li>
      </ul>
    </nav>
  </header>
</template>

<style scoped>
  .header {
    background-color: #333;
    color: #fff;
    padding: 10px 0;
  }

  .nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px;
  }

  .logo {
    font-size: 1.5rem;
    font-weight: bold;
  }

  .menu {
    list-style: none;
    display: flex;
    gap: 20px;
  }

  .menu li a {
    text-decoration: none;
    color: #fff;
  }
</style>