<script>
  import { createEventDispatcher } from 'svelte';

  export let primary = false;
  export let size = 'medium';
  export let label = '';

  const dispatch = createEventDispatcher();
   /**
   * Button click handler
   */
   function onClick(event) {
    dispatch('click', event);
  }
</script>

<button
  type="button"
  class={['stj-button', `stj-button--${size}`,
   `stj-button--${primary?'primary':'secondary'}`].join(' ')
   }
  on:click={onClick}>
  {label}
</button>

<style>
.stj-button {
    font-family: 'Nunito Sans', 'Helvetica Neue', Helvetica, Arial, sans-serif;
    font-weight: 700;
    border: 0;
    border-radius: 3px;
    cursor: pointer;
    display: inline-block;
    line-height: 1;
}
.stj-button--primary {
    color: #1b116e;
    background-color: #6bedb5;
}
.stj-button--secondary {
    color: #ffffff;
    background-color: #1b116e;
    box-shadow: rgba(0, 0, 0, 0.15) 0px 0px 0px 1px inset;
}
.stj-button--small {
    font-size: 12px;
    padding: 10px 16px;
}
.stj-button--medium {
    font-size: 14px;
    padding: 11px 20px;
}
.stj-button--large {
    font-size: 16px;
    padding: 12px 24px;
}

.stj-button--primary :hover {
    color: #1b116e;
    background-color: #55bd90;
}

.stj-button--primary :active {
    color: #1b116e;
    background-color: #55bd90;
    border: solid 2px #1b116e;
}

.stj-button--primary :disabled {
    color: #1b116e;
    opacity: 0.5;
    background-color: #6bedb5;
}

.stj-button--secondary :hover {
    color: #1b116e;
    background-color: #55bd90;
}

.stj-button--secondary :active {
    color: #1b116e;
    background-color: #6bedb5;
    border: solid 2px #1b116e;
}

.stj-button--secondary :disabled {
    color: #ffffff;
    opacity: 0.5;
    background-color: #1b116e;
}

</style>
