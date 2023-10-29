<script lang="ts">
  export let columns: string[] = [];
  export let data: any[] = [];
</script>

<style>
  .data-table {
    width: 100%;
    border-collapse: collapse;
    font-family: Arial, sans-serif;
    font-size: 14px;
    margin-bottom: 20px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    background-color: #fff; /* Set a background color for the table */
  }

  .data-table thead th {
    background-color: #f2f2f2;
    color: #333333;
    text-align: center; /* Center the header text */
    padding: 12px; /* Increase padding for better spacing */
    font-weight: bold;
    border-bottom: 1px solid #cccccc;
  }

  .data-table tbody td {
    padding: 12px; /* Increase padding for better spacing */
    border-bottom: 1px solid #cccccc;
    text-align: center; /* Center the cell content */
    vertical-align: middle; /* Center cell content vertically */
  }

  .data-table tbody tr:nth-child(even) {
    /* Apply alternating row colors */
    background-color: #f8f8f8;
  }

  .data-table tbody tr:hover {
    /* Apply hover effect */
    background-color: #f0f0f0;
  }
</style>

{#if data.length > 0}
  <table class="data-table">
    <thead>
      <tr>
        {#each columns as column (column)}
          <th>{column}</th>
        {/each}
      </tr>
    </thead>
    <tbody>
      {#each data as row (row.id)}
        <tr>
          {#each Object.values(row) as value (value)}
            <td>{value}</td>
          {/each}
        </tr>
      {/each}
    </tbody>
  </table>
{:else}
  <p>No data to display.</p>
{/if}
