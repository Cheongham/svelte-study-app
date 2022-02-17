<script>
   let fruits = ['Apple','banana','Chery','Orenge','Mango'];
</script>

<h2>
   Fruits
</h2>

<ul>
   {#each fruits as fruit }
      <li>{fruit}</li>
   {/each}
</ul>
<h2>
   Fruits Reverse
</h2>
<ul>
   {#each [...fruits.reverse()] as fruit }
      <li>{fruit}</li>
   {/each}
</ul>

<style></style>