<script lang="ts">
  import { sleep } from '$lib/sleep';
  import Table from '$lib/components/Table.svelte';

  var count = 1;

  let loading = false;

  const options = ['banana', 'apple'];
  let selected = '';
  let onChangeSelected = '';

  // simulated fetching
  async function getData() {
    loading = true;
    await sleep(500);
    count += 1;
    selected = onChangeSelected.trim();
    loading = false;
  }
</script>

<main class="container">
  <nav>
    <ul>
      <li><h3>The greatest app ever made</h3></li>
    </ul>
  </nav>

  <article>
    <header>
      <div class="grid">
        <div>
          <select bind:value={onChangeSelected} on:change={getData}>
            <option value="" disabled selected>Select a fruit</option>
            {#each options as option, i}
              <option>
                {option}
              </option>
            {/each}
          </select>
        </div>
        <div>
          <button aria-busy={loading} on:click={getData} disabled={loading}>
            {loading ? '' : '🔄'}
          </button>
        </div>
      </div>
    </header>

    <Table data={selected} {count} />

    <footer>
      <h6>Info</h6>
      <p>This is where information goes</p>
    </footer>
  </article>
</main>
