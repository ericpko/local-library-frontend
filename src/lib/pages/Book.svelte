<script lang="ts">
   async function getAllBooks() {
      try {
         let res = await fetch("http://localhost:4000/api/books");
         let books = await res.json();
         console.log(books);
         return books;
      } catch (err) {
         // console.error(err);
         throw new Error(err);
      }
   }

   let promise = getAllBooks();
</script>

<h1>Book List</h1>

{#await promise}
   <p>...fetching</p>
{:then books}
   <ul>
      {#each books as book}
         <li>{book.title}</li>
      {/each}
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
