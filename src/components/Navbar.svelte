<script>
    import { onMount } from "svelte";
    let menuOpen = false;
  
    function toggleMenu() {
      menuOpen = !menuOpen;
    }
  
    onMount(() => {
      const handleResize = () => {
        if (window.innerWidth >= 768) {
          menuOpen = false;
        }
      };
      window.addEventListener("resize", handleResize);
      return () => {
        window.removeEventListener("resize", handleResize);
      };
    });
  </script>
  
  <nav class="bg-gray-800 p-4">
    <div class="container mx-auto flex justify-between items-center">
      <a href="/" class="text-white text-lg font-bold">14Actual.com</a>
      <button
        class="text-white lg:hidden"
        on:click={toggleMenu}
      >
        {menuOpen ? '✕' : '☰'}
      </button>
      <div
        class={`${
          menuOpen ? "block" : "hidden"
        } lg:flex space-x-4`}
      >
        <a href="/" class="text-white">Home</a>
        <a href="/about" class="text-white">About</a>
      </div>
    </div>
  </nav>
  