<script>
	const sections = [
		{ id: 'objectives', label: 'Learning Objectives' },
		{ id: 'introduction', label: 'Introduction to Wokwi' },
		{ id: 'sign-in', label: 'Sign In / Sign Up' },
		{ id: 'esp32-template', label: 'ESP32 Starter Template' },
		{ id: 'initial-page', label: 'Initial Editor Page' },
		{ id: 'add-components', label: 'Adding Components' },
		{ id: 'connect-components', label: 'Connecting Components' },
		{ id: 'coding', label: 'Coding with Text Editor' },
		{ id: 'run-simulation', label: 'Running the Simulation' }
	];
</script>

<nav class="w-64 bg-white shadow-lg h-screen p-6 fixed left-0 top-0">
	<h2 class="text-xl font-bold mb-6 text-blue-700">ESP32 & Wokwi Module</h2>
	<ul class="space-y-2">
		{#each sections as section}
			<li>
				<a href="#{section.id}"
					class="block p-2 rounded hover:bg-blue-100 transition duration-200">
					{section.label}
				</a>
			</li>
		{/each}
	</ul>
	<div class="absolute bottom-6 left-6 text-sm text-gray-500">
		© 2025 Electronics Module Level 9
	</div>
</nav>