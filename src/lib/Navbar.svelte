<script>
   import Router from "svelte-spa-router";
   import Home from "./pages/Home.svelte";
   import Book from "./pages/Book.svelte";
   import Author from "./pages/Author.svelte";

   const routes = {
      // Exact path
      "/": Home,
      "/books": Book,
      "/authors": Author,
   };
</script>

<header>
   <nav>
      <ul>
         <li><a href="/">Home</a></li>
         <li><a href="/#/books">Books</a></li>
         <li><a href="/#/authors">Authors</a></li>
         <li><a href="/#/genres">Genres</a></li>
         <li><a href="/#/bookinstances">Book Instances</a></li>
      </ul>
   </nav>
</header>

<Router {routes} />

<style>
   header {
      /* border: 1px solid green; */
      /* margin-top: 0; */
      margin: 0;
      padding: 1em;
      background-color: #1a1a1a;
      /* FIXME */
      /* min-width: 920px; */
      width: 100%;
      position: fixed;
      top: 0;
      left: 0;
   }

   /* nav {
      border: 1px dotted white;
   } */

   ul {
      /* border: 1px solid red; */
      list-style: none;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 0;
      padding: 0;
      gap: 16px;
   }
</style>
