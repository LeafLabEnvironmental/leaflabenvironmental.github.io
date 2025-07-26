<script lang="ts">
	import { onMount } from 'svelte';

	let isdark = $state(false); // Initial state, will be updated in onMount

	// Media query list for checking system dark mode preference
	let mediaQuery: MediaQueryList | undefined;

	// Function to apply the theme based on the 'isdark' state
	function applyTheme(isDarkValue: boolean) {
		document.documentElement.setAttribute('data-theme', isDarkValue ? 'leaflab_dark' : 'leaflab');
		localStorage.setItem('isdark', JSON.stringify(isDarkValue));
	}

	onMount(() => {
		// 1. Check localStorage first (user's explicit preference)
		const storedValue = localStorage.getItem('isdark');

		if (storedValue !== null) {
			// If a value exists in localStorage, use it
			try {
				isdark = JSON.parse(storedValue);
			} catch (error) {
				console.error("Failed to parse 'isdark' from localStorage:", error);
				// Fallback to system preference or default if parsing fails
				isdark = window.matchMedia('(prefers-color-scheme: dark)').matches;
			}
		} else {
			// 2. If no value in localStorage, check system preference
			isdark = window.matchMedia('(prefers-color-scheme: dark)').matches;
		}

		// Apply the determined initial theme
		// We call applyTheme here because $effect might not run immediately on mount
		// or if `isdark` doesn't change from its initial `$state(false)`
		// if the storedValue or media query result is also false.
		applyTheme(isdark);

		// 3. Set up listener for system preference changes
		mediaQuery = window.matchMedia('(prefers-color-scheme: dark)');
		const handleMediaQueryChange = (event: MediaQueryListEvent) => {
			const currentStoredValue = localStorage.getItem('isdark');
			// Only change if no explicit choice, or if you want system preference to override
			// even if user previously set a manual preference (less common UX but possible)
			if (currentStoredValue === null) {
				isdark = event.matches;
				// The $effect below will then pick up this change and update theme/localStorage
			}
		};

		mediaQuery.addEventListener('change', handleMediaQueryChange);

		// Cleanup function for onMount
		return () => {
			mediaQuery?.removeEventListener('change', handleMediaQueryChange);
		};
	});

	// $effect to react to changes in `isdark` (from bind:checked or system preference listener)
	// This is where the theme application and localStorage saving happens when 'isdark' changes.
	$effect(() => {
		// Only apply/store if isdark is a boolean, ensuring it's properly initialized
		// This helps prevent issues during SSR or initial client hydration where `isdark`
		// might temporarily be `undefined` or its initial `$state(false)` value
		// before `onMount` has a chance to read from localStorage/mediaQuery.
		if (typeof isdark === 'boolean') {
			applyTheme(isdark);
		}
	});

	// The `toggleTheme` function is no longer strictly necessary for the toggle's function
	// because `bind:checked` handles the `isdark` state update.
	// I'll leave it as a commented-out example if you had other complex logic
	// you wanted to trigger *only* on a manual user interaction with the toggle,
	// distinct from programmatically changing `isdark`.
	// function toggleTheme() {
	//   isdark = !isdark;
	// }
</script>

<label class="flex cursor-pointer items-center gap-2">
	<svg
		xmlns="http://www.w3.org/2000/svg"
		width="20"
		height="20"
		viewBox="0 0 24 24"
		fill="none"
		stroke="currentColor"
		stroke-width="2"
		stroke-linecap="round"
		stroke-linejoin="round"
	>
		<circle cx="12" cy="12" r="5" />
		<path
			d="M12 1v2M12 21v2M4.2 4.2l1.4 1.4M18.4 18.4l1.4 1.4M1 12h2M21 12h2M4.2 19.8l1.4-1.4M18.4 5.6l1.4-1.4"
		/>
	</svg>
	<input type="checkbox" bind:checked={isdark} class="toggle theme-controller" />
	<svg
		xmlns="http://www.w3.org/2000/svg"
		width="20"
		height="20"
		viewBox="0 0 24 24"
		fill="none"
		stroke="currentColor"
		stroke-width="2"
		stroke-linecap="round"
		stroke-linejoin="round"
	>
		<path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path>
	</svg>
</label>
