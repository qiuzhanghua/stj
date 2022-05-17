<script>
  import { createEventDispatcher } from 'svelte';

  export let placeholder = '';
  export let label = '';
  export let disabled = false;

  export let value = '';

  export let state = "active";


  const dispatch = createEventDispatcher();

   /**
   * input change handler
   */
   function onChange(event) {
    dispatch('click', event);
  }
</script>

<label >

  {#if label}
      <span class="stj-input-label">{label}</span>
  {/if}


  <input
  disabled={disabled}
  type="text"
  class={['stj-input',`stj-input--${state}`].join(' ')}
  placeholder={placeholder}
  bind:value="{value}"
  >
</label>

<style>
  .stj-input {
  font-family: 'Nunito Sans', 'Helvetica Neue', Helvetica, Arial, sans-serif;
  font-weight: 700;
  min-height: 25px;
  margin: 2px;
  border-radius: 3px;
  border: solid 2px #353637;
  background-color: #ffffff;
}

.stj-input ::focus {
  border: solid 2px #1b116e;
}

.stj-input--success {
  border: solid 2px #067d68;
}

.stj-input--error {
  border: solid 2px #a9150b;
}

.stj-input--disabled {
  color: #e4e3ea;
  border: solid 2px #e4e3ea;
}

.stj-input ::-webkit-input-placeholder {
  color: red;
}

.stj-input-label {
  font-family: 'Nunito Sans', 'Helvetica Neue', Helvetica, Arial, sans-serif;
  font-weight: 700;
}

</style>