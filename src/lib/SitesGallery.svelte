<script>
  let activeIndex = 0;
  const panels = [
    {
      title: "Beautiful Landscape",
      image:
        "https://images.alphacoders.com/124/thumbbig-1249674.webp",
    },
    {
      title: "Serene Lake",
      image:
        "https://images2.alphacoders.com/118/thumbbig-1185562.webp",
    },
    {
      title: "Mountain View",
      image:
        "https://images3.alphacoders.com/118/thumbbig-1185563.webp",
    },
    {
      title: "Sunset Beach",
      image:
        "https://images2.alphacoders.com/133/thumbbig-1330681.webp",
    },
    {
      title: "City Skyline",
      image:
        "https://images4.alphacoders.com/754/thumbbig-754567.webp",
    },
  ];

  function handleKeyDown(event, index) {
    if (["Enter", " "].includes(event.key)) {
      event.preventDefault();
      activeIndex = index;
    }
  }
</script>

<main>
  <div class="title">
    <h1>Gallery-Jct</h1>
    <img class="title-image" src="/favicon.svg" alt="Logo" />
  </div>
  <div class="container">
    {#each panels as panel, index}
      <button
        class="panel {index === activeIndex ? 'active' : ''}"
        style="background-image: url('{panel.image}')"
        on:click={() => (activeIndex = index)}
        on:keydown={(e) => handleKeyDown(e, index)}
        aria-label={"Expandir imagen: " + panel.title}
      >
        <h3>{panel.title}</h3>
      </button>
    {/each}
  </div>
</main>

<style>
  /* Reset de estilos para botones */
  button.panel {
    border: none;
    background: none;
    padding: 0;
    margin: 10px;
    display: block;
    /* ... otros estilos existentes ... */
  }
  h3 {
    margin: 0.5rem;
    padding: 0.5rem;
    background-color: rgba(55, 77, 124, 0.651);
    border-radius: 0.5rem;
  }
  .title {
    background-color: rgba(14, 40, 59, 0.418);
  }
</style>
