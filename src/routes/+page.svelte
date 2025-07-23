<script>
	// Hero image URL - assuming LeafLabPhotoshootFixed.jpg is in your static/images folder
	const heroImageUrl = '/images/LeafLabPhotoshootFixed.jpg';
	const renderImageUrl = '/images/LeafLab3DRender.png'; // Assuming you have this 3D render image
	const contactEmail = 'contact@leaflab.io';

	let isMobileMenuOpen = false;

	// Function to handle smooth scrolling for navigation and close mobile menu
	function scrollToSection(id) {
		const element = document.getElementById(id);
		if (element) {
			element.scrollIntoView({ behavior: 'smooth' });
			isMobileMenuOpen = false; // Close menu after clicking a link
		}
	}

	// Toggle mobile menu visibility
	function toggleMobileMenu() {
		isMobileMenuOpen = !isMobileMenuOpen;
	}
</script>

<!-- Header Section -->
<header class="sticky top-0 z-50 bg-white shadow-md">
	<nav class="container mx-auto flex items-center justify-between px-4 py-4">
		<!-- Logo Container -->
		<a
			href="/"
			class="rounded-lg p-2 transition-colors hover:bg-green-50"
			aria-label="LeafLab Logo"
		>
			<!-- Simpler logo for desktop and larger screens -->
			<img src="favicon.svg" alt="LeafLab Icon" class="hidden h-8 w-auto md:block md:h-10" />
			<!-- Logo with text for mobile and medium screens -->
			<img
				src="default-monochrome.svg"
				alt="LeafLab Logo"
				class="block h-8 w-auto sm:h-10 md:hidden"
			/>
		</a>

		<!-- Navigation Links (Desktop) -->
		<div class="hidden space-x-8 md:flex">
			<button
				on:click={() => scrollToSection('home')}
				class="rounded-lg px-3 py-2 font-medium text-gray-700 transition-colors hover:text-green-700"
				>Home</button
			>
			<button
				on:click={() => scrollToSection('features')}
				class="rounded-lg px-3 py-2 font-medium text-gray-700 transition-colors hover:text-green-700"
				>Features</button
			>
			<button
				on:click={() => scrollToSection('quick-features')}
				class="rounded-lg px-3 py-2 font-medium text-gray-700 transition-colors hover:text-green-700"
				>At a Glance</button
			>
			<button
				on:click={() => scrollToSection('why-leaflab')}
				class="rounded-lg px-3 py-2 font-medium text-gray-700 transition-colors hover:text-green-700"
				>Why LeafLab?</button
			>
			<button
				on:click={() => scrollToSection('how-it-works')}
				class="rounded-lg px-3 py-2 font-medium text-gray-700 transition-colors hover:text-green-700"
				>How It Works</button
			>
			<button
				on:click={() => scrollToSection('accessories')}
				class="rounded-lg px-3 py-2 font-medium text-gray-700 transition-colors hover:text-green-700"
				>Accessories</button
			>
			<button
				on:click={() => scrollToSection('case-studies')}
				class="rounded-lg px-3 py-2 font-medium text-gray-700 transition-colors hover:text-green-700"
				>Success Stories</button
			>
		</div>

		<!-- Call to Action Button (Desktop) -->
		<a
			href="https://forms.gle/oKBZ6FcyaSpdVP3w8"
			target="_blank"
			class="hidden rounded-full bg-green-600 px-6 py-3 font-semibold text-white shadow-lg transition-all hover:bg-green-700 md:block"
		>
			Join Waitlist
		</a>

		<!-- Mobile Menu Button (Hamburger) -->
		<div class="md:hidden">
			<button
				on:click={toggleMobileMenu}
				class="text-gray-700 hover:text-green-700 focus:outline-none"
			>
				<!-- Hamburger/Close Icon (inline SVG for simplicity) -->
				{#if isMobileMenuOpen}
					<svg
						class="h-8 w-8"
						fill="none"
						stroke="currentColor"
						viewBox="0 0 24 24"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M6 18L18 6M6 6l12 12"
						></path>
					</svg>
				{:else}
					<svg
						class="h-8 w-8"
						fill="none"
						stroke="currentColor"
						viewBox="0 0 24 24"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M4 6h16M4 12h16M4 18h16"
						></path>
					</svg>
				{/if}
			</button>
		</div>
	</nav>

	<!-- Mobile Navigation Menu -->
	{#if isMobileMenuOpen}
		<div
			class="origin-top transform bg-white pb-4 shadow-lg transition-all duration-300 ease-in-out md:hidden"
			class:scale-y-0={!isMobileMenuOpen}
			class:scale-y-100={isMobileMenuOpen}
		>
			<nav class="flex flex-col items-center space-y-4 px-4">
				<button
					on:click={() => scrollToSection('home')}
					class="w-full py-2 text-center font-medium text-gray-700 hover:text-green-700"
					>Home</button
				>
				<button
					on:click={() => scrollToSection('features')}
					class="w-full py-2 text-center font-medium text-gray-700 hover:text-green-700"
					>Features</button
				>
				<button
					on:click={() => scrollToSection('quick-features')}
					class="w-full py-2 text-center font-medium text-gray-700 hover:text-green-700"
					>At a Glance</button
				>
				<button
					on:click={() => scrollToSection('why-leaflab')}
					class="w-full py-2 text-center font-medium text-gray-700 hover:text-green-700"
					>Why LeafLab?</button
				>
				<button
					on:click={() => scrollToSection('how-it-works')}
					class="w-full py-2 text-center font-medium text-gray-700 hover:text-green-700"
					>How It Works</button
				>
				<button
					on:click={() => scrollToSection('accessories')}
					class="w-full py-2 text-center font-medium text-gray-700 hover:text-green-700"
					>Accessories</button
				>
				<button
					on:click={() => scrollToSection('case-studies')}
					class="w-full py-2 text-center font-medium text-gray-700 hover:text-green-700"
					>Success Stories</button
				>
				<a
					href="https://forms.gle/oKBZ6FcyaSpdVP3w8"
					target="_blank"
					class="mt-2 w-full rounded-full bg-green-600 px-6 py-3 text-center font-semibold text-white shadow-lg transition-all hover:bg-green-700"
				>
					Join Waitlist
				</a>
			</nav>
		</div>
	{/if}
</header>

<!-- Hero Section -->
<section
	id="home"
	class="relative flex h-screen w-full items-center justify-center overflow-hidden bg-gray-900 text-center"
>
	<!-- Background Image with Overlay -->
	<img
		src={heroImageUrl}
		alt="LeafLab Environmental Controller for Grow Rooms"
		class="absolute inset-0 h-full w-full object-cover object-center opacity-70"
	/>
	<div class="absolute inset-0 bg-gradient-to-t from-gray-900 via-gray-900/50 to-transparent"></div>

	<!-- Hero Content -->
	<div class="relative z-10 mx-auto max-w-5xl p-6 text-white md:p-10">
		<h1 class="mb-4 text-4xl leading-tight font-extrabold md:text-6xl">
			LeafLab: Your Plants' Personal Growth Coach!
		</h1>
		<p class="mb-6 text-lg font-light opacity-95 md:text-2xl">
			Unleash Unrivalled Precision and Wireless Control for Truly Optimised Grow Room Environments.
		</p>
		<p class="text-md mx-auto mb-10 max-w-3xl opacity-80 md:text-lg">
			Experience the future of cultivation with LeafLab – intelligently managing every aspect of
			your grow, ensuring peak plant health and maximum yields. Compatible with virtually any grow
			room equipment from any manufacturer, providing you with unparalleled freedom and flexibility.
		</p>
		<button
			on:click={() => scrollToSection('features')}
			class="transform rounded-full bg-green-600 px-8 py-4 text-lg font-semibold text-white shadow-xl transition-all hover:scale-105 hover:bg-green-700"
		>
			Discover Advanced Features
		</button>
	</div>
</section>

<!-- Features Section -->
<section id="features" class="bg-gray-50 py-16">
	<div class="container mx-auto px-4 text-center">
		<h2 class="mb-12 text-4xl font-bold text-gray-800">Precision Engineered for Prolific Growth</h2>
		<div class="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-3">
			<!-- Feature Card 1: Wireless Equipment Control & Compatibility -->
			<div
				class="transform rounded-xl bg-white p-8 shadow-lg transition-shadow hover:-translate-y-2 hover:shadow-xl"
			>
				<div class="mb-4 text-green-600">
					<svg
						class="mx-auto h-12 w-12"
						fill="currentColor"
						stroke="none"
						viewBox="0 0 24 24"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M13.68 24.8h-2.28v-11.56c0-0.48-0.36-0.84-0.84-0.84s-0.84 0.36-0.84 0.84v11.56h-2.28c-0.48 0-0.84 0.36-0.84 0.84s0.36 0.84 0.84 0.84h6.24c0.44 0 0.84-0.4 0.84-0.84 0-0.48-0.36-0.84-0.84-0.84zM12.88 16.4c-0.2 0-0.44-0.080-0.6-0.24-0.32-0.32-0.32-0.84 0-1.2 0.48-0.48 0.72-1.080 0.72-1.72s-0.24-1.28-0.72-1.72c-0.32-0.32-0.32-0.84 0-1.2 0.32-0.32 0.84-0.32 1.2 0 0.76 0.76 1.2 1.8 1.2 2.92s-0.44 2.12-1.2 2.92c-0.16 0.16-0.4 0.24-0.6 0.24zM15.2 18.72c-0.2 0-0.44-0.080-0.6-0.24-0.32-0.32-0.32-0.84 0-1.2 1.080-1.080 1.68-2.52 1.68-4.040s-0.6-2.96-1.68-4.080c-0.32-0.32-0.32-0.84 0-1.2 0.32-0.32 0.84-0.32 1.2 0 1.4 1.4 2.16 3.28 2.16 5.24 0 2-0.76 3.84-2.16 5.24-0.16 0.2-0.36 0.28-0.6 0.28zM17.44 20.96c-0.2 0-0.44-0.080-0.6-0.24-0.32-0.32-0.32-0.84 0-1.2 1.68-1.68 2.6-3.92 2.6-6.28s-0.92-4.6-2.6-6.28c-0.32-0.32-0.32-0.84 0-1.2 0.32-0.32 0.84-0.32 1.2 0 2 2 3.080 4.64 3.080 7.48 0 2.8-1.080 5.48-3.080 7.48-0.2 0.16-0.4 0.24-0.6 0.24zM7.64 16.16c-0.76-0.8-1.2-1.8-1.2-2.92s0.44-2.16 1.2-2.92c0.36-0.32 0.88-0.32 1.2 0 0.32 0.36 0.32 0.88 0 1.2-0.48 0.44-0.72 1.080-0.72 1.72s0.24 1.24 0.72 1.72c0.32 0.36 0.32 0.88 0 1.2-0.16 0.16-0.4 0.24-0.6 0.24s-0.44-0.080-0.6-0.24zM5.32 18.44c-1.4-1.4-2.16-3.24-2.16-5.24 0-1.96 0.76-3.84 2.16-5.24 0.36-0.32 0.88-0.32 1.2 0 0.32 0.36 0.32 0.88 0 1.2-1.080 1.12-1.68 2.56-1.68 4.080s0.6 2.96 1.68 4.040c0.32 0.36 0.32 0.88 0 1.2-0.16 0.16-0.4 0.24-0.6 0.24-0.24 0-0.44-0.080-0.6-0.28zM3.080 20.72c-2-2-3.080-4.68-3.080-7.48 0-2.84 1.080-5.48 3.080-7.48 0.36-0.32 0.88-0.32 1.2 0 0.32 0.36 0.32 0.88 0 1.2-1.68 1.68-2.6 3.92-2.6 6.28s0.92 4.6 2.6 6.28c0.32 0.36 0.32 0.88 0 1.2-0.16 0.16-0.4 0.24-0.6 0.24s-0.4-0.080-0.6-0.24z"
						></path>
					</svg>
				</div>
				<h3 class="mb-3 text-2xl font-semibold text-gray-800">
					Universal Wireless Equipment Control
				</h3>
				<p class="text-gray-600">
					LeafLab connects wirelessly to virtually any piece of grow room equipment, from any
					manufacturer. This means unparalleled flexibility and no more messy cables or proprietary
					lock-ins. It's the central nervous system for your entire grow operation.
				</p>
			</div>

			<!-- Feature Card 2: Advanced Lighting Control -->
			<div
				class="transform rounded-xl bg-white p-8 shadow-lg transition-shadow hover:-translate-y-2 hover:shadow-xl"
			>
				<div class="mb-4 text-green-600">
					<svg
						class="mx-auto h-12 w-12"
						fill="currentColor"
						stroke="none"
						viewBox="0 0 24 24"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M7.32 5.36c-4.040 0-7.32 3.28-7.32 7.32 0 2.56 1.32 4.92 3.52 6.24v3.92c0 2.080 1.72 3.8 3.8 3.8s3.8-1.72 3.8-3.8v-3.92c2.2-1.32 3.52-3.68 3.52-6.28 0-4-3.28-7.28-7.32-7.28zM7.32 24.96c-1.16 0-2.12-0.96-2.12-2.12v-1.040c0.68 0.2 1.4 0.32 2.12 0.32s1.44-0.12 2.12-0.32v1.040c0 1.2-0.92 2.12-2.12 2.12zM9.92 17.68c-0.28 0.12-0.48 0.44-0.48 0.76v1.56c-0.68 0.28-1.4 0.4-2.12 0.4-0.76 0-1.44-0.16-2.12-0.4v-1.56c0-0.24-0.12-0.52-0.32-0.68-0.040-0.040-0.080-0.080-0.16-0.080-1.88-0.96-3.040-2.88-3.040-5 0-3.12 2.52-5.64 5.64-5.64s5.64 2.52 5.64 5.64c0 2.12-1.16 4.040-3.040 5zM9.44 12.32c-0.64-0.44-1.36-0.64-2.12-0.64s-1.52 0.24-2.12 0.64c-0.4 0.24-0.48 0.8-0.24 1.16 0.16 0.24 0.44 0.36 0.68 0.36 0.16 0 0.32-0.040 0.48-0.16 0.72-0.48 1.68-0.48 2.36 0 0.4 0.24 0.92 0.16 1.16-0.24 0.28-0.32 0.2-0.84-0.2-1.12z"
						></path>
					</svg>
				</div>
				<h3 class="mb-3 text-2xl font-semibold text-gray-800">
					Sophisticated Lighting & Fan Management
				</h3>
				<p class="text-gray-600">
					Go beyond simple on/off. LeafLab provides granular control over your grow lights,
					including realistic sunrise and sunset effects for natural plant cycles. It can even
					intelligently adjust lighting output to aid with temperature control, seamlessly
					integrating with your environment. Fan speeds are precisely managed for optimal airflow
					and exhaust.
				</p>
			</div>

			<!-- Feature Card 3: Customisable Grow Profiles -->
			<div
				class="transform rounded-xl bg-white p-8 shadow-lg transition-shadow hover:-translate-y-2 hover:shadow-xl"
			>
				<div class="mb-4 text-green-600">
					<svg
						class="mx-auto h-12 w-12"
						fill="currentColor"
						stroke="none"
						viewBox="0 0 24 24"
						xmlns="http://www.w3.org/2000/svg"
						><path
							d="M5.859,8.341a5.876,5.876,0,0,0,5.283.117A9,9,0,0,0,11,10v2H6a1,1,0,0,0-1,1v3a1,1,0,0,0,1,1H7v5a1,1,0,0,0,1,1h8a1,1,0,0,0,1-1V17h1a1,1,0,0,0,1-1V13a1,1,0,0,0-1-1H13V10a7.008,7.008,0,0,1,7-7,1,1,0,0,0,0-2,8.993,8.993,0,0,0-7.642,4.27C11.415,3.55,9.155,1,4,1A1,1,0,0,0,3,2C3,2.187,3.033,6.594,5.859,8.341ZM15,21H9V17h6Zm2-6H7V14H17ZM10.756,6.471c-1.635.677-2.924.736-3.841.172-1.154-.711-1.646-2.383-1.826-3.6C8.8,3.375,10.238,5.366,10.756,6.471Z"
						></path></svg
					>
				</div>
				<h3 class="mb-3 text-2xl font-semibold text-gray-800">
					Customisable Grow Profiles with Minute Resolution
				</h3>
				<p class="text-gray-600">
					Craft bespoke environmental profiles tailored to your plants' exact needs at different
					growth stages. Set distinct day and night conditions for temperature, humidity, and CO₂,
					with schedules adjustable to the precise minute. This level of detail ensures your plants
					get exactly what they need, exactly when they need it.
				</p>
			</div>

			<!-- Feature Card 4: Precision Climate Mastery -->
			<div
				class="transform rounded-xl bg-white p-8 shadow-lg transition-shadow hover:-translate-y-2 hover:shadow-xl"
			>
				<div class="mb-4 text-green-600">
					<svg
						class="mx-auto h-12 w-12"
						fill="none"
						stroke="currentColor"
						viewBox="0 0 24 24"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M15 4H20M15 8H20M17 12H20M8 15.9998C7.44772 15.9998 7 16.4475 7 16.9998C7 17.5521 7.44772 17.9998 8 17.9998C8.55228 17.9998 9 17.5521 9 16.9998C9 16.4475 8.55228 15.9998 8 15.9998ZM8 15.9998V9M8 16.9998L8.00707 17.0069M12 16.9998C12 19.209 10.2091 20.9998 8 20.9998C5.79086 20.9998 4 19.209 4 16.9998C4 15.9854 4.37764 15.0591 5 14.354L5 6C5 4.34315 6.34315 3 8 3C9.65685 3 11 4.34315 11 6V14.354C11.6224 15.0591 12 15.9854 12 16.9998Z"
							stroke="currentColor"
							stroke-width="2"
							stroke-linecap="round"
							stroke-linejoin="round"
						></path>
					</svg>
				</div>
				<h3 class="mb-3 text-2xl font-semibold text-gray-800">
					Advanced Temperature & Humidity Control
				</h3>
				<p class="text-gray-600">
					Maintain incredibly stable warmth and moisture levels. LeafLab’s intelligent algorithms
					constantly monitor and make micro-adjustments, providing an unshakeable environment where
					your plants will consistently exceed expectations. It's truly set-and-forget, with optimal
					conditions guaranteed.
				</p>
			</div>

			<!-- Feature Card 5: Comprehensive Data Insights & Offline Reliability -->
			<div
				class="transform rounded-xl bg-white p-8 shadow-lg transition-shadow hover:-translate-y-2 hover:shadow-xl"
			>
				<div class="mb-4 text-green-600">
					<svg class="mx-auto h-12 w-12" viewBox="0 0 50 50">
						<path
							d="M7.854 33.546 16 22.893l7.52 16.293 6.267-27.572 3.76 8.773 5.64-6.893 3.76 8.146"
							style="fill:none;stroke:currentColor;stroke-width:2.50658;stroke-linecap:round;stroke-linejoin:round"
						></path>
					</svg>
				</div>
				<h3 class="mb-3 text-2xl font-semibold text-gray-800">
					In-Depth Data Logging & Offline Resilience
				</h3>
				<p class="text-gray-600">
					Every critical environmental data point is meticulously logged, offering invaluable
					insights into your grow's history and trends. With an optional RTC (Real-Time Clock)
					module, LeafLab maintains precise scheduling and data integrity even if Wi-Fi or power is
					interrupted. Your data is always accurate and available.
				</p>
			</div>

			<!-- Feature Card 6: Intuitive Control & Monitoring -->
			<div
				class="transform rounded-xl bg-white p-8 shadow-lg transition-shadow hover:-translate-y-2 hover:shadow-xl"
			>
				<div class="mb-4 text-green-600">
					<!-- Wifi/Remote Control Icon (Phosphor Icons - DeviceMobile) -->
					<svg class="mx-auto h-12 w-12" fill="currentColor" viewBox="0 0 256 256"
						><path
							d="M168,24H88A24,24,0,0,0,64,48V208a24,24,0,0,0,24,24h80a24,24,0,0,0,24-24V48A24,24,0,0,0,168,24ZM128,216a12,12,0,1,1,12-12A12,12,0,0,1,128,216ZM176,48V184H80V48Z"
						></path></svg
					>
				</div>
				<h3 class="mb-3 text-2xl font-semibold text-gray-800">
					User-Friendly Interface for Total Control
				</h3>
				<p class="text-gray-600">
					Access and manage your LeafLab through a beautifully designed, intuitive interface – via
					your smartphone, tablet, or computer. Real-time dashboards provide instant environmental
					snapshots, allowing you to make quick adjustments or simply enjoy peace of mind from
					anywhere in the world.
				</p>
			</div>
		</div>
	</div>
</section>

<!-- Quick Features List Section -->
<section id="quick-features" class="bg-white py-12">
	<div class="container mx-auto px-4 text-center">
		<h2 class="mb-8 text-4xl font-bold text-gray-800">LeafLab at a Glance</h2>
		<div class="text-md mx-auto max-w-4xl space-y-4 text-left text-gray-700">
			<ul class="list-inside list-disc space-y-2">
				<li>
					<strong>Wireless Equipment Control</strong> Seamlessly connect to virtually any grow room equipment.
				</li>
				<li>
					<strong>Universal Compatibility</strong> Works with devices from any manufacturer, no proprietary
					lock-ins.
				</li>
				<li>
					<strong>Sophisticated Lighting Control</strong> Mimic natural sunrise/sunset, and adjust output
					for temperature.
				</li>
				<li>
					<strong>Precise Fan Management</strong> Optimise airflow and exhaust with granular control.
				</li>
				<li>
					<strong>Custom Grow Profiles</strong> Create detailed day/night schedules with minute resolution.
				</li>
				<li>
					<strong>Real-time Data Logging</strong> Track temperature, humidity, CO₂, and more for informed
					decisions.
				</li>
				<li>
					<strong>Offline Resilience</strong> Optional RTC module ensures schedules and data integrity
					even without Wi-Fi.
				</li>
				<li>
					<strong>Air Conditioning Integration</strong> Control your AC unit with an optional accessory
					for ultimate climate stability.
				</li>
				<li>
					<strong>Intuitive User Interface</strong> Manage your grow from anywhere via smartphone, tablet,
					or computer.
				</li>
				<li>
					<strong>Scalable & Future-Proof</strong> Easily expand capabilities with a range of essential
					accessories.
				</li>
			</ul>
		</div>
	</div>
</section>

<!-- Render Image Section (Optional, if you want to highlight the 3D render separately) -->
<section
	id="render"
	class="relative flex h-screen w-full items-center justify-center overflow-hidden bg-gray-900 text-center"
>
	<img
		src={renderImageUrl}
		alt="LeafLab Environmental Controller 3D Render"
		class="absolute inset-0 h-full w-full object-cover object-center"
	/>
</section>

<!-- Why LeafLab Section -->
<section id="why-leaflab" class="bg-green-700 py-16 text-white">
	<div class="container mx-auto px-4 text-center">
		<h2 class="mb-12 text-4xl font-bold">Why LeafLab Stands Apart?</h2>
		<div class="mx-auto grid max-w-5xl grid-cols-1 gap-10 md:grid-cols-2">
			<div class="text-left">
				<h3 class="mb-3 text-2xl font-semibold">True Wireless Freedom</h3>
				<p class="opacity-90">
					Unlike basic controllers with limited ports or complex wiring, LeafLab liberates your grow
					space with truly wireless equipment control. This means a tidier setup, easier expansion,
					and the flexibility to arrange your equipment exactly as you need it.
				</p>
			</div>
			<div class="text-left">
				<h3 class="mb-3 text-2xl font-semibold">Unmatched Equipment Compatibility</h3>
				<p class="opacity-90">
					Why be limited? LeafLab is designed to work seamlessly with virtually any grow room
					equipment from any manufacturer. Whether it's a new LED light or an existing humidifier,
					LeafLab integrates, giving you full control without forced upgrades or brand loyalty.
				</p>
			</div>
			<div class="text-left">
				<h3 class="mb-3 text-2xl font-semibold">Precision Control, Simplified</h3>
				<p class="opacity-90">
					Many controllers offer basic automation. LeafLab provides sophisticated, minute-by-minute
					control over every environmental factor. Our intuitive system means you get advanced
					functionality without the steep learning curve – it's powerful, yet delightfully simple to
					use.
				</p>
			</div>
			<div class="text-left">
				<h3 class="mb-3 text-2xl font-semibold">Adaptive Lighting for Natural Growth</h3>
				<p class="opacity-90">
					Beyond simple timers, LeafLab's intelligent lighting control mimics natural light cycles,
					fostering healthier plant development. It can even adjust lighting output in real-time to
					help stabilise room temperature, a feature rarely seen in conventional controllers,
					ensuring peak efficiency.
				</p>
			</div>
			<div class="text-left md:col-span-2">
				<h3 class="mb-3 text-2xl font-semibold">Scalable & Future-Proof</h3>
				<p class="opacity-90">
					As your growing needs evolve, so can LeafLab. Its modular design and comprehensive
					accessory range mean you can easily expand its capabilities, ensuring your investment
					continues to pay dividends for years to come. It’s a solution that grows with you, not one
					you’ll outgrow.
				</p>
			</div>
		</div>
	</div>
</section>

<!-- How It Works Section -->
<section id="how-it-works" class="bg-white py-16">
	<div class="container mx-auto px-4 text-center">
		<h2 class="mb-12 text-4xl font-bold text-gray-800">Cultivating Perfection, Simplified.</h2>
		<p class="mx-auto mb-10 max-w-3xl text-lg text-gray-600">
			LeafLab takes the complexity out of environmental control. Here's the simplified process:
		</p>
		<div class="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-4">
			<!-- Step 1 -->
			<div class="flex flex-col items-center rounded-xl border border-gray-200 p-6 shadow-sm">
				<div
					class="mb-4 flex h-16 w-16 items-center justify-center rounded-full bg-green-100 text-3xl font-bold text-green-600"
				>
					1
				</div>
				<h3 class="mb-2 text-xl font-semibold text-gray-800">Tailor Your Profile</h3>
				<p class="text-gray-600">
					Easily create custom grow profiles with distinct day/night settings for temperature,
					humidity, and CO₂, scheduled to the minute for precise control.
				</p>
			</div>
			<!-- Step 2 -->
			<div class="flex flex-col items-center rounded-xl border border-gray-200 p-6 shadow-sm">
				<div
					class="mb-4 flex h-16 w-16 items-center justify-center rounded-full bg-green-100 text-3xl font-bold text-green-600"
				>
					2
				</div>
				<h3 class="mb-2 text-xl font-semibold text-gray-800">Sensors Deliver Live Data</h3>
				<p class="text-gray-600">
					Your included temperature and humidity sensors (and any chosen add-ons) continuously feed
					real-time environmental data to your LeafLab controller.
				</p>
			</div>
			<!-- Step 3 -->
			<div class="flex flex-col items-center rounded-xl border border-gray-200 p-6 shadow-sm">
				<div
					class="mb-4 flex h-16 w-16 items-center justify-center rounded-full bg-green-100 text-3xl font-bold text-green-600"
				>
					3
				</div>
				<h3 class="mb-2 text-xl font-semibold text-gray-800">LeafLab Orchestrates Your Grow</h3>
				<p class="text-gray-600">
					Based on your profiles and live data, LeafLab intelligently activates and finely adjusts
					your grow room equipment (lights, fans, humidifiers, CO₂ emitters, etc.) wirelessly to
					maintain ideal conditions.
				</p>
			</div>
			<!-- Step 4 -->
			<div class="flex flex-col items-center rounded-xl border border-gray-200 p-6 shadow-sm">
				<div
					class="mb-4 flex h-16 w-16 items-center justify-center rounded-full bg-green-100 text-3xl font-bold text-green-600"
				>
					4
				</div>
				<h3 class="mb-2 text-xl font-semibold text-gray-800">Monitor, Analyse & Thrive</h3>
				<p class="text-gray-600">
					Access detailed environmental logs and current conditions via our intuitive interface.
					Review your data, make informed adjustments, and witness your plants' exceptional growth.
				</p>
			</div>
		</div>
	</div>
</section>

<!-- Accessories Section -->
<section id="accessories" class="bg-gray-200 py-16">
	<div class="container mx-auto px-4 text-center">
		<h2 class="mb-12 text-4xl font-bold text-gray-800">
			Expand Your Control: Essential Accessories
		</h2>
		<p class="mx-auto mb-10 max-w-3xl text-lg text-gray-600">
			Your LeafLab controller comes with a high-precision temperature and relative humidity sensor,
			along with three smart plugs, ready to get you started. For even greater control and insight,
			explore our range of optional add-ons:
		</p>
		<div class="mx-auto grid max-w-6xl grid-cols-1 gap-8 md:grid-cols-1 lg:grid-cols-2">
			<!-- Accessory 1: CO2 Sensor -->
			<div class="rounded-xl bg-white p-8 shadow-lg transition-shadow hover:shadow-xl">
				<div class="mb-4 text-green-600">
					<svg class="mx-auto h-12 w-12" fill="currentColor" viewBox="0 0 512 512">
						<path
							d="M236.234,300.093c6.524,0,11.451-2.283,15.063-6.979c3.716-4.83,5.6-11.241,5.6-19.055v-19.266 c0-7.662-1.905-13.996-5.664-18.825c-3.66-4.704-8.59-6.99-15.071-6.99c-6.465,0-11.315,2.265-14.829,6.923 c-3.629,4.812-5.469,11.168-5.469,18.893v19.266c0,7.819,1.863,14.234,5.537,19.066 C224.961,297.813,229.814,300.093,236.234,300.093z"
						></path>
						<path
							d="M400.444,220.561c3.321-10.508,5.001-21.422,5.001-32.523c0-59.535-48.435-107.97-107.969-107.97 c-36.11,0-70.11,18.412-90.006,48.394c-15.298-10.923-33.797-16.886-52.667-16.886c-49.978,0-90.638,40.66-90.638,90.639 c0,5.925,0.575,11.824,1.712,17.602C27.97,227.549,0,261.358,0,300.538c0,45.438,36.966,82.404,82.403,82.404h298.205 c45.437,0,82.402-36.967,82.402-82.404C463.01,262.331,437.021,229.555,400.444,220.561z M175.683,247.879l-0.835,2.513h-24.989 v-2.5c0-6.322-1.474-11.162-4.382-14.387c-2.841-3.149-7.485-4.746-13.804-4.746c-5.562,0-9.855,2.197-13.125,6.717 c-3.407,4.706-5.134,10.859-5.134,18.29v21.175c0,7.504,1.813,13.69,5.389,18.388c3.464,4.552,8.031,6.765,13.962,6.765 c5.876,0,10.211-1.52,12.883-4.518c2.745-3.08,4.137-7.876,4.137-14.251v-2.5H174.7l0.837,2.511l0.006,0.384 c0.205,12.095-3.578,21.863-11.244,29.035c-7.608,7.118-18.218,10.727-31.535,10.727c-13.415,0-24.482-4.396-32.896-13.068 c-8.395-8.648-12.651-19.895-12.651-33.425v-21.05c0-13.465,4.149-24.702,12.333-33.397c8.226-8.739,19.033-13.17,32.122-13.17 c13.69,0,24.598,3.613,32.42,10.74c7.9,7.199,11.801,17.086,11.596,29.386L175.683,247.879z M283.166,273.968 c0,13.624-4.391,25.065-13.051,34.006c-8.681,8.963-20.079,13.507-33.881,13.507c-13.709,0-25.025-4.547-33.633-13.515 c-8.582-8.939-12.934-20.378-12.934-33.998v-19.084c0-13.569,4.337-24.994,12.892-33.957c8.586-8.995,19.891-13.557,33.602-13.557 c13.799,0,25.211,4.557,33.918,13.544c8.684,8.966,13.087,20.395,13.087,33.97V273.968z M376.656,319.951h-77.4v-17.397 l34.979-37.503c4.75-5.45,8.195-10.133,10.185-13.857c1.883-3.525,2.837-6.793,2.837-9.712c0-3.893-0.986-6.95-3.014-9.348 c-1.923-2.271-4.646-3.375-8.325-3.375c-4.119,0-7.127,1.312-9.197,4.011c-2.193,2.863-3.307,6.824-3.307,11.771v2.5h-24.985 l-0.837-2.499l-0.01-0.375c-0.26-10.225,3.155-19.01,10.152-26.109c6.987-7.092,16.47-10.688,28.184-10.688 c11.517,0,20.745,3.087,27.431,9.174c6.753,6.149,10.177,14.417,10.177,24.573c0,6.871-1.912,13.297-5.685,19.099 c-3.583,5.511-9.539,12.79-17.704,21.638l-15.346,16.709h41.866V319.951z"
						></path></svg
					>
				</div>
				<h3 class="mb-3 text-2xl font-semibold text-gray-800">CO₂ Sensor</h3>
				<p class="text-gray-600">
					Accurately monitor carbon dioxide levels to boost plant growth. Essential for cultivators
					looking to maximise photosynthesis and yields.
				</p>
			</div>
			<!-- Accessory 2: Contactless IR Temperature Sensor -->
			<div class="rounded-xl bg-white p-8 shadow-lg transition-shadow hover:shadow-xl">
				<div class="mb-4 text-green-600">
					<svg class="mx-auto h-12 w-12" fill="currentColor" stroke="none" viewBox="0 0 20 20">
						<path
							d="m 7.296875 -0.0117188 c -0.078125 0 -0.160156 0.0039063 -0.234375 0.0117188 c -0.453125 0.0507812 -0.882812 0.222656 -1.25 0.5 c -0.488281 0.371094 -0.8125 0.957031 -0.8125 1.6875 v 3.8125 h -2.273438 c -0.402343 0 -0.726562 0.324219 -0.726562 0.726562 v 6.546876 c 0 0.402343 0.324219 0.726562 0.726562 0.726562 h 5.546876 c 0.402343 0 0.726562 -0.324219 0.726562 -0.726562 v -6.546876 c 0 -0.402343 -0.324219 -0.726562 -0.726562 -0.726562 h -2.273438 v -3.8125 c 0 -0.449219 0.171875 -0.703125 0.4375 -0.90625 s 0.664062 -0.300781 1.0625 -0.28125 s 0.785156 0.152344 1.0625 0.40625 s 0.46875 0.585938 0.46875 1.125 c 0 2.164062 1.464844 3.507812 3 3.46875 c 0.855469 -0.023438 1.6875 -0.476562 2.25 -1.3125 l -0.5625 -1 c -0.375 0.914062 -1.066406 1.296875 -1.71875 1.3125 c -0.960938 0.023438 -1.96875 -0.730469 -1.96875 -2.46875 c 0 -0.792969 -0.335938 -1.445312 -0.8125 -1.875 s -1.082031 -0.6289062 -1.6875 -0.65625 c -0.074219 -0.00390625 -0.15625 -0.0078125 -0.234375 -0.0117188 z m 6.703125 2.0117188 v 0.125 l 0.78125 1.375 c 0.011719 -0.039062 0.019531 -0.082031 0.03125 -0.125 z m 0 0.34375 c -0.007812 0.105469 -0.019531 0.214844 -0.03125 0.3125 l 0.71875 1.21875 c 0.023438 -0.0625 0.042969 -0.121094 0.0625 -0.1875 z m -0.0625 0.5 c -0.015625 0.089844 -0.042969 0.167969 -0.0625 0.25 l 0.65625 1.125 c 0.03125 -0.0625 0.066406 -0.125 0.09375 -0.1875 z m -0.09375 0.4375 c -0.023438 0.089844 -0.066406 0.167969 -0.09375 0.25 l 0.59375 1.03125 c 0.039062 -0.066406 0.089844 -0.117188 0.125 -0.1875 z m 0 0"
						></path>
					</svg>
				</div>
				<h3 class="mb-3 text-2xl font-semibold text-gray-800">Contactless IR Temperature Sensor</h3>
				<p class="text-gray-600">
					Measure surface temperatures of plants or grow medium without contact, providing a more
					accurate understanding of plant health and stress.
				</p>
			</div>
			<!-- Accessory 3: RTC Module -->
			<div class="rounded-xl bg-white p-8 shadow-lg transition-shadow hover:shadow-xl">
				<div class="mb-4 text-green-600">
					<svg class="mx-auto h-12 w-12" fill="none" stroke="currentColor" viewBox="0 0 32 32">
						<path
							d="M3 5.5L5 3.5M21 5.5L19 3.5M9 12.5L11 14.5L15 10.5M20 12.5C20 16.9183 16.4183 20.5 12 20.5C7.58172 20.5 4 16.9183 4 12.5C4 8.08172 7.58172 4.5 12 4.5C16.4183 4.5 20 8.08172 20 12.5Z"
							stroke="currentColor"
							stroke-width="2"
							stroke-linecap="round"
							stroke-linejoin="round"
						></path></svg
					>
				</div>
				<h3 class="mb-3 text-2xl font-semibold text-gray-800">RTC (Real-Time Clock) Module</h3>
				<p class="text-gray-600">
					Ensures precise schedule keeping and accurate data logging, even during internet outages
					or power interruptions. Critical for uninterrupted operations.
				</p>
			</div>
			<!-- Accessory 4: AC Control Module -->
			<div class="rounded-xl bg-white p-8 shadow-lg transition-shadow hover:shadow-xl">
				<div class="mb-4 text-green-600">
					<svg class="mx-auto h-12 w-12" fill="currentColor" viewBox="0 0 448 384">
						<path
							d="M413,282.988H99c-5.522,0-10-4.477-10-10v-113c0-5.523,4.478-10,10-10h314c5.522,0,10,4.477,10,10v113 C423,278.511,418.522,282.988,413,282.988z M109,262.988h294v-93H109V262.988z"
						></path>
						<path
							d="M378.687,282.988c-0.006,0-0.013,0-0.02,0H136.001c-3.161,0-6.136-1.494-8.022-4.03c-1.887-2.536-2.464-5.814-1.556-8.842 l12.498-41.682c1.269-4.23,5.162-7.127,9.579-7.127h215c4.204,0,7.96,2.63,9.397,6.581l14.946,41.075 c0.542,1.232,0.843,2.594,0.843,4.026C388.687,278.511,384.21,282.988,378.687,282.988z M149.439,262.988h214.947l-7.89-21.682 H155.941L149.439,262.988z"
						></path>
						<path
							d="M148.001,198.655h-16.667c-5.522,0-10-4.477-10-10s4.478-10,10-10h16.667c5.522,0,10,4.477,10,10 S153.523,198.655,148.001,198.655z"
						></path>
						<path
							d="M159.334,362.012c-5.522,0-10-4.477-10-10v-44.714c0-5.523,4.478-10,10-10s10,4.477,10,10v44.714 C169.334,357.535,164.856,362.012,159.334,362.012z"
						></path>
						<path
							d="M245.334,362.012c-5.522,0-10-4.477-10-10v-44.714c0-5.523,4.478-10,10-10s10,4.477,10,10v44.714 C255.334,357.535,250.856,362.012,245.334,362.012z"
						></path>
						<path
							d="M331.334,362.012c-5.522,0-10-4.477-10-10v-44.714c0-5.523,4.478-10,10-10s10,4.477,10,10v44.714 C341.334,357.535,336.856,362.012,331.334,362.012z"
						></path></svg
					>
				</div>
				<h3 class="mb-3 text-2xl font-semibold text-gray-800">
					Air Conditioning Control Accessory
				</h3>
				<p class="text-gray-600">
					Integrate your air conditioning unit for comprehensive temperature management. This
					accessory allows LeafLab to precisely control cooling, maintaining consistent grow room
					climate year-round.
				</p>
			</div>
		</div>
	</div>
</section>

<!-- Case Studies / Success Stories Section -->
<section id="case-studies" class="bg-green-800 py-16 text-white">
	<div class="container mx-auto px-4 text-center">
		<h2 class="mb-12 text-4xl font-bold">Hear From Our Thriving Growers</h2>
		<div class="mx-auto grid max-w-4xl grid-cols-1 gap-8 md:grid-cols-2">
			<div class="rounded-xl bg-white p-8 text-gray-800 shadow-lg">
				<p class="mb-4 text-lg italic">
					"LeafLab transformed my yields! I've never seen such consistent growth. The wireless
					control is brilliant, making setup a breeze and giving me so much more flexibility."
				</p>
				<p class="font-semibold text-green-700">- Alex, Urban Grower, London</p>
			</div>
			<div class="rounded-xl bg-white p-8 text-gray-800 shadow-lg">
				<p class="mb-4 text-lg italic">
					"The data logging alone is worth its weight in gold. Being able to analyse trends and
					fine-tune my environment has made a massive difference to my harvests. Plus, those
					sunrise/sunset effects are truly stunning!"
				</p>
				<p class="font-semibold text-green-700">- Priya, Commercial Cultivator, Manchester</p>
			</div>
		</div>
	</div>
</section>

<!-- Final Call to Action Section -->
<section class="bg-green-600 py-16 text-center text-white">
	<div class="container mx-auto px-4">
		<h2 class="mb-6 text-4xl font-bold">Ready to Revolutionise Your Grow?</h2>
		<p class="mx-auto mb-10 max-w-3xl text-xl opacity-90">
			Join the growing number of cultivators who are achieving unparalleled results with LeafLab.
			Take control of your environment and grow smarter, not harder.
		</p>
		<a
			href="https://forms.gle/oKBZ6FcyaSpdVP3w8"
			target="_blank"
			class="transform rounded-full bg-white px-10 py-5 text-xl font-bold text-green-700 shadow-xl transition-all hover:scale-105 hover:bg-gray-200"
		>
			Join The Waitlist Today!
		</a>
	</div>
</section>

<!-- Footer Section -->
<footer class="bg-gray-800 py-10 text-gray-300">
	<div
		class="container mx-auto grid grid-cols-1 gap-8 px-4 text-center md:grid-cols-3 md:text-left"
	>
		<!-- Logo & Copyright -->
		<div class="mx-auto">
			<a href="/" class="text-2xl font-bold text-green-500 transition-colors hover:text-green-400">
				<img src="default-monochrome.svg" width="400" alt="LeafLab Logo" class="h-10 w-auto" />
			</a>
			<p class="mt-2 text-sm">&copy; {new Date().getFullYear()} LeafLab. All rights reserved.</p>
		</div>

		<!-- Navigation Links -->
		<div class="md:text-center">
			<h3 class="mb-3 text-lg font-semibold text-white">Quick Links</h3>
			<ul>
				<li class="mb-2">
					<button
						on:click={() => scrollToSection('home')}
						class="transition-colors hover:text-white">Home</button
					>
				</li>
				<li class="mb-2">
					<button
						on:click={() => scrollToSection('features')}
						class="transition-colors hover:text-white">Features</button
					>
				</li>
				<li class="mb-2">
					<button
						on:click={() => scrollToSection('quick-features')}
						class="transition-colors hover:text-white">At a Glance</button
					>
				</li>
				<li class="mb-2">
					<button
						on:click={() => scrollToSection('why-leaflab')}
						class="transition-colors hover:text-white">Why LeafLab?</button
					>
				</li>
				<li class="mb-2">
					<button
						on:click={() => scrollToSection('how-it-works')}
						class="transition-colors hover:text-white">How It Works</button
					>
				</li>
				<li class="mb-2">
					<button
						on:click={() => scrollToSection('accessories')}
						class="transition-colors hover:text-white">Accessories</button
					>
				</li>
			</ul>
		</div>

		<!-- Contact & Social -->
		<div class="md:text-right">
			<h3 class="mb-3 text-lg font-semibold text-white">Get in Touch</h3>
			<p class="mb-2">
				Email: <a href={`mailto:${contactEmail}`} class="text-green-400 hover:underline"
					>{contactEmail}</a
				>
			</p>
			<div class="mt-4 flex justify-center space-x-4 md:justify-end">
				<a
					href="https://www.instagram.com/leaflabenvironmental/"
					class="text-gray-300 transition-colors hover:text-white"
					aria-label="Instagram"
				>
					<svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
						<path
							fill-rule="evenodd"
							d="M12 0C8.74 0 8.333.014 7.053.072 5.773.132 4.912.333 4.148.636 3.375.948 2.671 1.455 2.068 2.068.953 3.181.333 4.912.072 7.053.014 8.333 0 8.74 0 12s.014 3.673.072 4.953c.06 1.28.261 2.141.564 2.913.312.772.819 1.476 1.432 2.089.613.613 1.317 1.12 2.089 1.432.772.303 1.633.504 2.913.564C8.333 23.986 8.74 24 12 24s3.673-.014 4.953-.072c1.28-.06 2.141-.261 2.913-.564.772-.312 1.476-.819 2.089-1.432.613-.613 1.12-1.317 1.432-2.089.303-.772.504-1.633.564-2.913.058-1.28.072-1.687.072-4.953s-.014-3.673-.072-4.953c-.06-1.28-.261-2.141-.564-2.913-.312-.772-.819-1.476-1.432-2.089C21.18 2.812 20.475 2.305 19.703 2.002c-.772-.303-1.633-.504-2.913-.564C15.673.014 15.26 0 12 0zm0 2.16c3.2 0 3.586.012 4.85.071 1.17.055 1.7.249 2.05.385.35.136.59.317.81.53.22.213.4.453.53.81.136.35.33.88.385 2.05.059 1.264.071 1.65.071 4.85s-.012 3.586-.071 4.85c-.055 1.17-.249 1.7-.385 2.05-.136.35-.317.59-.53.81-.213.22-.453.4-.81.53-.35.136-.88.33-2.05.385-1.264.059-1.65.071-4.85.071s-3.586-.012-4.85-.071c-1.17-.055-1.7-.249-2.05-.385-.35-.136-.59-.317-.81-.53-.22-.213-.4-.453-.53-.81-.136-.35-.33-.88-.385-2.05-.059-1.264-.071-1.65-.071-4.85s.012-3.586.071-4.85c.055-1.17.249-1.7.385-2.05.136-.35.317-.59.53-.81.213.22.453.4.81.53.35-.136.88-.33 2.05-.385C8.414 2.172 8.79 2.16 12 2.16zM12 6.865c-2.835 0-5.135 2.3-5.135 5.135s2.3 5.135 5.135 5.135 5.135-2.3 5.135-5.135-2.3-5.135-5.135-5.135zM12 15.4c-1.87 0-3.39-1.52-3.39-3.39s1.52-3.39 3.39-3.39 3.39 1.52 3.39 3.39-1.52 3.39-3.39 3.39zm5.135-8.83c-.783 0-1.417.634-1.417 1.417s.634 1.417 1.417 1.417 1.417-.634 1.417-1.417-.634-1.417-1.417-1.417z"
							clip-rule="evenodd"
						></path>
					</svg>
				</a>
			</div>
		</div>
	</div>
</footer>
