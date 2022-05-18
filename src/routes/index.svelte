<script>
  import '../styles.css'
import Toggle from "../lib/Toggle.svelte";
import Button from "../lib/Button.svelte";
import Input from "../lib/Input.svelte";

  const onButton = (event) => {
    alert(value);
  };
  
  let isToggled = false;

  let value = '';

</script>

<h1>Welcome to Svelte Components</h1>

<Input label="Input" bind:value={value} placeholder='Input your name' ></Input>

<Button label='Primary Button' size='large' on:click={onButton}></Button>

