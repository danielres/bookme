<script>
  import { page } from '$app/stores'
  const { section } = $page.params

  const promise = fetch('/api').then((res) => res.json())
</script>

<p>{section}</p>

{#await promise}
  Pending...
{:then value}
  {JSON.stringify(value)}
{:catch error}
  {JSON.stringify(error)}
{/await}
