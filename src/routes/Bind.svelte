<script>
   // 데이터 바인딩을 연습한다 (input checkbox 등 ...)

   let name= "이청함";
   let yes= true;
   let options = [
      {coin : 1, simbol: "BTC"},
      {coin : 2, simbol: "ETC"},
      {coin : 3, simbol: "XRP"},
      {coin : 4, simbol: "BTT"}
   ];
   let selectedOption = 1;
</script>


<input type="text" bind:value={name} />
<p>Hello {name}</p>

<div style='background-color:green;'>-</div>

<lable> 
   <input type="checkbox" bind:checked={yes} />체크박스 테스트 </lable>

{#if yes}
   <p>YES</p>
{:else}
   <p>NO</p>
{/if}

<div style='background-color:green;'>-</div>

<select bind:value={selectedOption}>
   {#each options as opt}
      <option value={opt.coin}>{opt.simbol}</option>
   {/each}
</select>
<p> Select options ::: {selectedOption} </p>

<div style='background-color:green;'>-</div>


<style></style>