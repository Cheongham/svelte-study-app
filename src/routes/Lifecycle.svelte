<script>
   // 컴포넌트의 Lifecycle을 알아본다
   // onMount(),afterUpdate(),beforeUpdate(),onDestroy()
   import {onMount, onDestroy, afterUpdate, beforeUpdate} from "svelte";

   let seconds = 0;
   let interval = window.setInterval(() => {
      seconds = seconds + 1;
   }, 1000);

   //컴포넌트 마운트 완료시 이벤트 작동
   onMount(() => {
      //alert("onMount");
   });

   //컴포넌트 마운트 종료시 이벤트 작동
   onDestroy(() => {
      //alert("onDestroy");
      window.clearInterval(interval);
   });

   //DOM이 업데이트 직전 이벤트 작동
   beforeUpdate(() => {
      console.log("beforeUpdate");
   });

   //DOM이 업데이트 직후 이벤트 작동
   afterUpdate(() => {
      console.log("afterUpdate");
   });
   
   let count =0;
   function addCount() {
      count = count + 1 ;
   }

</script>


<h1> 안녕하세요 {seconds}</h1>

<button type ="button" on:click={addCount}> 카운터 증가 </button>
<p>Count : {count} </p>