<script lang="ts">
   async function getCollectionCounts() {
      try {
         let res = await fetch("http://localhost:4000");
         let counts = await res.json();
         // console.log(counts);
         return counts;
      } catch (err) {
         // console.error(err);
         throw new Error(err);
      }
   }

   let promise = getCollectionCounts();
</script>

<h1>Local Library</h1>
<p>Welcome to the Local Library, a full-stack tutorial website.</p>

<p>The library has the following record counts:</p>

{#await promise}
   <p>...fetching</p>
{:then counts}
   <ul>
      <li>Authors: {counts.authors}</li>
      <li>Books: {counts.books}</li>
      <li>Genres: {counts.genres}</li>
      <li>Book Instances: {counts.bookinstances}</li>
   </ul>
{:catch error}
   <p style="color: red">{error.message}</p>
{/await}

<style>
   li {
      color: #646cff;
      font-weight: bold;
   }

   li:hover {
      color: #535bf2;
   }
</style>
