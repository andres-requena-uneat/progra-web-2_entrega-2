<script>
  let num1 = 17;
  let num2 = 42;

  $: addition = num1 + num2;
  $: subtraction = num1 - num2;
  $: multiplication = num1 * num2;
  $: division = num2 !== 0 ? (num1 / num2).toFixed(2) : 'Undefined';
</script>

<div>
  <h1>Ejemplo #1</h1>
  <div class="container">
    <div class="input">
      <label for="num1">Number 1:</label>
      <input type="number" id="num1" bind:value={num1} />
    </div>
  
    <div class="input">
      <label for="num2">Number 2:</label>
      <input type="number" id="num2" bind:value={num2} />
    </div>
  
    <div>
      <p>Addition: {addition}</p>
      <p>Subtraction: {subtraction}</p>
      <p>Multiplication: {multiplication}</p>
      <p>Division: {division}</p>
    </div>
  </div>
</div>