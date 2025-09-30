<script>
  export let src = 'https://www.gimkit.com/practice/68d9b715e20570aa68dd8a9a';

  // Function to enter fullscreen mode
  function enterFullscreen() {
    const iframe = document.getElementById('quiz-frame');
    if (iframe) {
      if (iframe.requestFullscreen) {
        iframe.requestFullscreen();
      } else if (iframe.webkitRequestFullscreen) { /* Safari */
        iframe.webkitRequestFullscreen();
      } else if (iframe.msRequestFullscreen) { /* IE11 */
        iframe.msRequestFullscreen();
      }
    }
  }
</script>

<div class="my-6 relative">
  <h3 class="text-lg font-semibold mb-2">Try the Quiz Live</h3>

  <!-- Main iframe with ID -->
  <iframe
    id="quiz-frame"
    {src}
    title="Quiz ESP32 - Blinking LED"
    width="100%"
    height="450"
    class="border rounded-lg shadow-md w-full"
    allow="fullscreen"
    loading="lazy"
  ></iframe>

  <!-- Full Screen Button -->
  <button
    on:click={enterFullscreen}
    class="absolute bottom-2 right-2 bg-blue-600 hover:bg-blue-700 text-white text-sm font-medium px-3 py-1 rounded shadow-md transition"
    aria-label="Open simulation in full screen mode"
  >
    ⛶ Full Screen
  </button>
</div>