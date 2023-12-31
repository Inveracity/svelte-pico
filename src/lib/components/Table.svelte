<script lang="ts">
  export let data: string;
  export let count: number;

  let setData: string = '';

  $: switch (data) {
    case 'banana':
      setData = '🍌';
      break;
    case 'apple':
      setData = '🍎';
      break;
    default:
      setData = data;
  }

</script>

<table>
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">{data}</th>
      <th scope="col">{data}</th>
      <th scope="col">{data}</th>
      <th scope="col">{data}</th>
      <th scope="col">{data}</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">{count}</th>
      <td>{setData}</td>
      <td>{setData}</td>
      <td>{setData}</td>
      <td>{setData}</td>
      <td>{setData}</td>
    </tr>
    <tr>
      <th scope="row">{count}</th>
      <td>{setData}</td>
      <td>{setData}</td>
      <td>{setData}</td>
      <td>{setData}</td>
      <td>{setData}</td>
    </tr>
    <tr>
      <th scope="row">{count}</th>
      <td>{setData}</td>
      <td>{setData}</td>
      <td>{setData}</td>
      <td>{setData}</td>
      <td>{setData}</td>
    </tr>
  </tbody>
</table>
