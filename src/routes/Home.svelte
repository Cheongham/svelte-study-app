<!-- svelte 문법 연습 -->

<script>
   import Nested from "../components/Nested.svelte";

   let name = "이청함님 환영 합니다!!!";
   let src = "https://madewithnetworkfra.fra1.digitaloceanspaces.com/spatie-space-production/28498/svelte-cubed.jpg";
   let htmlName = "<span style='color:red;'> 굿맨님 환영 합니다!!! </span> ";

   let count = 0;
   function increseCount() {
      count = count + 1 ;
   }

   // $:는 vue의 watch 와 비슷한 기능으로 'count'라는 값이 변경되면 즉시 반영이 된다
   // 예문 1
   $: if (count > 5 ) {
      alert("카운터는 5보다 클수 없습니다");
      count = 5;
   }
   // 예문 1
   let sum = 0;
   $: sum = count * 2 ;


   let arrData = [
      {coin : "비트코인", simbol: "BTC"},
      {coin : "이더리움", simbol: "ETC"},
      {coin : "리플", simbol: "XRP"},
      {coin : "비트토렌트", simbol: "BTT"}
   ];
</script>

<div style='background-color:green;'>-</div>

<h1>Hello {name}</h1>
<img {src} alt="이미지" />
<h1>Hello {@html htmlName}</h1>
<button type="button" on:click={increseCount}> 증가 </button>
<div>Count ::: {count} </div>
<div>Sum ::: {sum} </div>

<div style='background-color:green;'>-</div>

<!-- ** 외부 페이지와 연결하기 -->
<Nested name1={name} />

<div style='background-color:green;'>-</div>

<!-- 렌드링 관련 연습 -->
{#if count < 3}
   <div>Count1 :: {count}</div>
{:else}
   <div>Count2 :: {count}</div>
{/if}

<div style='background-color:green;'>-</div>

<!-- 멀티 데이타 (Array) 처리 -->
<table>
   {#each arrData as {coin, simbol}, i}
      <tr>
         <td>{coin}</td>
         <td>{simbol}</td>
      </tr>
   {/each}
</table>

<style>
   img {
      width: 300px;
      height: 150px;
      object-fit: cover;
   }
</style>