<script>
  // Se definen dos variables que cuyo valor cambiara
  let num1 = 17;
  let num2 = 42;

  // Se definen cuatro variables reactivas. Estas toman los valores definidos arriba
  // y realizan diferentes calculos con ellos.
  $: addition = num1 + num2;
  $: subtraction = num1 - num2;
  $: multiplication = num1 * num2;
  $: division = num2 !== 0 ? (num1 / num2).toFixed(2) : 'Undefined';
</script>

<div>
  <h1>Ejemplo #1</h1>
  <div class="container">
    <div class="input">
      <!-- Se muestra/edita el valor del primer numero -->
      <label for="num1">Number 1:</label>
      <input type="number" id="num1" bind:value={num1} />
    </div>
  
    <div class="input">
      <!-- Se muestra/edita el valor del segundo numero -->
      <label for="num2">Number 2:</label>
      <input type="number" id="num2" bind:value={num2} />
    </div>
  
    <div>
      <!-- Aqui se muestran los valores calculados anteriormente -->
      <p>Addition: {addition}</p>
      <p>Subtraction: {subtraction}</p>
      <p>Multiplication: {multiplication}</p>
      <p>Division: {division}</p>
    </div>
  </div>
</div>