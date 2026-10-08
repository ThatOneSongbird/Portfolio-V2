<!-- Logic Section -->
<script>
  let menuOverlay;

  function openMenu() {
    menuOverlay.showModal();
  }

  function closeMenu() {
    menuOverlay.close();
  }

  function handleBackdropClick(event) {
    if (event.target === menuOverlay) closeMenu();
  }
</script>

<!-- Button Section -->
<button class = "menu-button" onclick={openMenu} aria-label="Open menu">
  <span></span>
  <span></span>
</button>

<!-- Dialog Section -->
<dialog bind:this={menuOverlay} onclick={handleBackdropClick}>
  <nav>
    <a href="/about">About Me</a>
    <a href="/projects">Projects</a>
    <details>
        <summary>Contact</summary>
        <a href="https://www.linkedin.com/in/ian-johnson-b55a67382" target="_blank" rel="noopener noreferrer">LinkedIn</a>
        <a href="https://github.com/ThatOneSongbird" target="_blank" rel="noopener noreferrer">Github</a>
        <a href="n/a">Email</a>
    </details>
    <a href="/dossier">Dossier</a>
  </nav>
  <button class ="close-button" onclick={closeMenu}>Close</button>
</dialog>

<!-- Style Section-->
 <style>
    dialog {
      text-align: center;
    }
    nav {
        display: flex;
        flex-direction: column;
        gap: 1rem;
        align-items: center;
    }
    .close-button {
      margin-top: 2rem;
    }
    .menu-button {
      position: fixed;
      top: 1.5rem;
      right: 1.5rem;
      z-index:10;
    }
    .menu-button span{
      display: block;
      width: 2rem;
      height: 2px;
      background: whitesmoke;
    }
 </style>