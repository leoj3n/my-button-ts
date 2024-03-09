<script lang="ts">
	import type { HTMLButtonAttributes } from 'svelte/elements';

	interface $$Props extends HTMLButtonAttributes {
		/** What should my name be? */
		myName: string;
		/** My custom prop! */
		myCustomProp: boolean;
	}

	export let myName: $$Props['myName'] = 'Foo';
	export let myCustomProp: $$Props['myCustomProp'];
</script>

<button {...$$restProps}>
	{myName}
	{#if myCustomProp}isTrue{/if}
	<slot />
</button>

<!--
@component
Here's some documentation for this component...

## Usage
- Simple usage:
```tsx
<MyButton>Foo</MyButton>
```
- Advanced usage:
```tsx
<MyButton myName="Foo" myCustomProp={true}>Bar</MyButton>
```

## Props
@prop export let myCustomProp: boolean;
@prop export let myName: string;
-->
