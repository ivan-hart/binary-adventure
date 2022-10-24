<script>
  const binaryString = "Binary: "
  const decimalString = "Decimal: "

  $: binary = '0'
  $: decimal = 0

  function increment() {
    decimal++
    binary = decimal.toString(2)
  }
  function decrement() {
    decimal--
    binary = decimal.toString(2)
  }
</script>

<main>
  <div class="container wraper">
    <div class="container bg-dark">
      <div id="integer">Integer: {decimal}</div>
      <div id="binary">Binary: {binary}</div>
    </div>
    <div class="btns">
      <button on:click="{() => {increment()}}">Increment</button>
      <button on:click="{() => {decrement()}}">Decrement</button>
    </div>
    <div class="reset-btn">
      <button on:click={() => {decimal = 0; binary = '0'}}>Reset</button>
    </div>
</div>
</main>

<style>
  main {
    background-image: url('./assets/header.svg');
    background-repeat: no-repeat;
    height: 100vh;
    color: #fff;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .container {
    background-color: #ffffff33;
    padding: 30px;
    border-radius: 10px;
  }
  .wraper {
    width: 100%;
    max-width: 500px;
  }
  #integer {
    margin-block: 10px;
  }
  #binary {
    margin-block: 10px;
  }
  .bg-dark {
    background-color: #000;
  }
  .btns {
    margin-top: 20px;
    width: 100%;
    display: flex;
    justify-content: space-around;
  }
  button {
    width: 100%;
    max-width: 150px;
    border: none;
    background-color:crimson;
    border-radius: 5px;
    height: 4em;
  }
  button:hover {
    background-color: red;
  }
  button:active {
    background: #aa0000;
  }
  .reset-btn {
    margin-top: 20px;
    display: flex;
    justify-content: center;
  }
</style>