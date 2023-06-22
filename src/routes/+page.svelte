<script>
  let map_infos = [
    {
      files: ["map_test_full"],
      text: "Full map",
    },
    {
      files: ["map_test_bot", "map_test_mid", "map_test_top"],
      text: "Top map",
    },
    {
      files: ["map_test_bot", "map_test_mid"],
      text: "Mid map",
    },
    {
      files: ["map_test_bot"],
      text: "Bottom map",
    },
  ];

  let selected = map_infos[0];
</script>

<select bind:value={selected}>
  {#each map_infos as map_info}
    <option value={map_info}>
      {map_info.text}
    </option>
  {/each}
</select>

<div class="map_div">
  {#each selected.files as file_name}
    {#if file_name == selected.files.at(-1) && selected.files.length != 1}
      <img
        class="top_image"
        src="/{file_name}.webp"
        alt="fuck u"
        height="512"
        width="512"
      />
    {:else}
      <img src="/{file_name}.webp" alt="fuck u" height="512" width="512" />
    {/if}
  {/each}
</div>

<style>
  .map_div > img {
    position: absolute;
  }

  .top_image {
    filter: drop-shadow(0 0 10px blue);
  }
</style>
