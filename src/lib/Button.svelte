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
    @apply font-normal border-0 rounded-lg cursor-pointer inline-block leading-none;
}
    
.stj-button--primary {
    @apply text-[#1b116e] bg-[#6bedb5];
}

.stj-button--secondary {
    @apply text-[#fff] bg-[#1b116e] shadow-[0px_0px_0px_1px_rgba(0,0,0,0.15)_inset];
    box-shadow: rgba(0, 0, 0, 0.15) 0px 0px 0px 1px inset;
}

.stj-button--small {
    @apply text-xs px-2.5 py-4;
}

.stj-button--medium {
    @apply text-sm px-[11px] py-5;
}

.stj-button--large {
    @apply text-base px-3 py-6;
}

.stj-button--primary :hover {
    @apply text-[#1b116e] bg-[#55bd90];
}

.stj-button--primary :active {
    @apply text-[#1b116e] bg-[#55bd90] border-solid border-2 border-[#1b116e];
}

.stj-button--primary :disabled {
    @apply text-[#1b116e]/0.5 bg-[#6bedb5];
}

.stj-button--secondary :hover {
    @apply text-[#1b116e] bg-[#55bd90];
}

.stj-button--secondary :active {
    @apply text-[#1b116e] bg-[#55bd90] border-solid border-2 border-[#1b116e];

}

.stj-button--secondary :disabled {
    @apply text-white bg-[#1b116e]/0.5;
}

</style>
