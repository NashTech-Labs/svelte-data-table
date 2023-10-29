<script lang="ts">
  import  SvelteTable from "../svelteTable.svelte";

  let columns = ['ID', 'Name', 'Age', 'Email'];
  let data = [
    { ID: 1, Name: 'John Doe', Age: 30, Email: 'john@example.com' },
    { ID: 2, Name: 'Jane Doe', Age: 28, Email: 'jane@example.com' },
    { ID: 3, Name: 'Bob Smith', Age: 35, Email: 'bob@example.com' },
  ];
</script>

<SvelteTable  {columns} {data} />