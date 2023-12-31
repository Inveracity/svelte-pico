<script lang="ts">
  import { sleep } from '$lib/sleep';

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
    selected = onChangeSelected;
    loading = false;
  }
</script>

<main class="container">
  <div class="grid">
    <div>
      <select bind:value={onChangeSelected} on:change={getData}>
        <option value="" disabled selected>Select</option>
        {#each options as option, i}
          <option>{option}</option>
        {/each}
      </select>
    </div>
    <button aria-busy={loading} class="outline" on:click={getData} disabled={loading}>
      {loading ? '' : '🔄'}
    </button>
  </div>
  <div>
    <table>
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">Heading</th>
          <th scope="col">Heading</th>
          <th scope="col">Heading</th>
          <th scope="col">Heading</th>
          <th scope="col">Heading</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th scope="row">{count}</th>
          <td>{selected}</td>
          <td>{selected}</td>
          <td>{selected}</td>
          <td>{selected}</td>
          <td>{selected}</td>
        </tr>
        <tr>
          <th scope="row">{count}</th>
          <td>{selected}</td>
          <td>{selected}</td>
          <td>{selected}</td>
          <td>{selected}</td>
          <td>{selected}</td>
        </tr>
        <tr>
          <th scope="row">{count}</th>
          <td>{selected}</td>
          <td>{selected}</td>
          <td>{selected}</td>
          <td>{selected}</td>
          <td>{selected}</td>
        </tr>
      </tbody>
    </table>
  </div>
</main>
