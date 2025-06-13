<script>
  let isMenuOpen = false;
  let isScrolled = false;

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }

  function closeMenu() {
    isMenuOpen = false;
  }

  function handleScroll() {
    isScrolled = window.scrollY > 10;
  }
</script>

<svelte:window on:scroll={handleScroll} />

<header class="sticky top-0 z-50 flex justify-center py-4">
  <div class="relative flex w-auto items-center justify-center gap-4 rounded-lg px-6 py-2 transition-colors duration-300 md:gap-10
    {isScrolled
      ? 'bg-background/80 backdrop-blur-sm shadow-lg'
      : 'bg-main'}"
  >
    <a href="/" class="text-lg font-bold text-white">Edward Diesta</a>
    <nav class="hidden md:flex">
      <ul class="flex items-center gap-6 text-sm text-gray-400">
        <li><a href="#projects" class="hover:text-white">Projects</a></li>
        <li><a href="#tech-stack" class="hover:text-white">Tech Stack</a></li>
        <li><a href="#about" class="hover:text-white">About</a></li>
        <li><a href="/" class="hover:text-white">Blog</a></li>
      </ul>
    </nav>
    <div class="md:hidden">
      <button
        type="button"
        on:click={toggleMenu}
        aria-controls="mobile-menu"
        aria-expanded={isMenuOpen}
        class="inline-flex items-center justify-center rounded-md p-2 text-gray-400 hover:bg-gray-700 hover:text-white focus:outline-none"
      >
        <span class="sr-only">Open main menu</span>
        <svg
          class="block h-6 w-6"
          class:hidden={isMenuOpen}
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
        >
          <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
        </svg>
        <svg
          class="h-6 w-6"
          class:hidden={!isMenuOpen}
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
        >
          <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>
    </div>
  </div>
</header>

{#if isMenuOpen}
  <!-- Overlay -->
  <div
    class="fixed inset-0 z-[99] bg-black/40 md:hidden"
    on:click={closeMenu}
    style="pointer-events: auto;"
  ></div>
  <!-- Centered Menu Panel -->
  <div
    id="mobile-menu"
    class="fixed left-1/2 top-1/2 z-[100] flex justify-center items-center w-full md:hidden"
    style="transform: translate(-50%, -50%); pointer-events: auto;"
  >
    <div
      class="relative rounded-2xl bg-background/90 backdrop-blur-lg shadow-2xl px-8 py-10 flex flex-col gap-6 w-[90vw] max-w-xs"
      on:click|stopPropagation
    >
      <!-- Close button -->
      <button
        class="absolute top-4 right-4 rounded-full p-2 text-gray-400 hover:bg-gray-800/60 hover:text-white transition-colors text-2xl"
        on:click={closeMenu}
        aria-label="Close menu"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          stroke-width="2"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M6 18L18 6M6 6l12 12"
          />
        </svg>
      </button>

      <!-- Add on:click={closeMenu} to each link -->
      <a
        href="#projects"
        class="block text-lg font-semibold text-gray-100 rounded-lg px-4 py-3 transition hover:bg-gray-800/60 hover:text-white focus:bg-gray-800/80 focus:outline-none"
        on:click={closeMenu}>Projects</a
      >
      <a
        href="#tech-stack"
        class="block text-lg font-semibold text-gray-100 rounded-lg px-4 py-3 transition hover:bg-gray-800/60 hover:text-white focus:bg-gray-800/80 focus:outline-none"
        on:click={closeMenu}>Tech Stack</a
      >
      <a
        href="#about"
        class="block text-lg font-semibold text-gray-100 rounded-lg px-4 py-3 transition hover:bg-gray-800/60 hover:text-white focus:bg-gray-800/80 focus:outline-none"
        on:click={closeMenu}>About</a
      >
      <a
        href="/"
        class="block text-lg font-semibold text-gray-100 rounded-lg px-4 py-3 transition hover:bg-gray-800/60 hover:text-white focus:bg-gray-800/80 focus:outline-none"
        on:click={closeMenu}>Blog</a
      >
    </div>
  </div>
{/if}