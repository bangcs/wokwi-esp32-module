<script>
	import Sidebar from '$lib/components/Sidebar.svelte';
	import CodeBlock from '$lib/components/CodeBlock.svelte';
	import EmbeddedSimulation from '$lib/components/EmbeddedSimulation.svelte';
    import Note from '$lib/components/Note.svelte';
</script>

<div class="flex min-h-screen bg-gray-50">
	<Sidebar />
<main class="ml-64 p-8 max-w-4xl mx-auto flex-grow">
	<header class="mb-10">
		<h1 class="text-4xl font-extrabold text-gray-900">Electronics Module Level 9: Learning Wokwi & ESP32</h1>
		<p class="text-lg text-gray-600">Simulate microcontroller projects without physical hardware.</p>
	</header>

	<!-- Learning Objectives -->
<section id="objectives" class="mb-12">
	<h2 class="text-2xl font-bold mb-4 text-blue-700">🎯 Learning Objectives</h2>
	<ul class="list-disc list-inside space-y-2 ml-4 bg-white p-6 rounded-lg shadow">
		<li>Explain what Wokwi is and its benefits in microcontroller simulation.</li>
		<li>Create an account and sign in to the Wokwi platform using Google, GitHub, or email.</li>
		<li>Identify the main interface of Wokwi, especially the <strong>My Projects</strong> section and <strong>Starter Template</strong> for ESP32.</li>
		<li>Add electronic components (such as LED, resistor, button) to a simulation project using Wokwi’s component library.</li>
		<li>Connect components to ESP32 pins virtually through drag-and-connect interface.</li>
		<li>Write basic Arduino (C++) code to configure pin modes (<code class="bg-gray-200 px-1 rounded">pinMode</code>) and control digital output (<code class="bg-gray-200 px-1 rounded">digitalWrite</code>).</li>
		<li>Run a simulation on Wokwi and observe circuit behavior (e.g., lighting up an LED).</li>
		<li>Understand the basic structure of a microcontroller program: <code class="bg-gray-200 px-1 rounded">setup()</code> and <code class="bg-gray-200 px-1 rounded">loop()</code>.</li>
	</ul>
</section>

<!-- Introduction to Wokwi -->
<section id="introduction" class="mb-12">
	<h2 class="text-2xl font-bold mb-4">Introduction to Wokwi</h2>
	<p>
		Wokwi is an online platform designed for simulating microcontrollers such as Arduino, ESP32, STM32, and Raspberry Pi. 
		It specializes particularly in ESP32 simulations, offering powerful features like internet data transfer simulation and integration with third-party platforms such as Blynk and MQTT.
		Premium users can even connect to private networks.
	</p>
	<img src="/images/Pasted_image_20250919141508.png" alt="Wokwi homepage" class="my-4 border rounded-lg shadow-md w-full" />
	<p>
		Visit <a href="https://wokwi.com" class="text-blue-600 underline">wokwi.com</a>. You'll see four supported board categories on the homepage. 
		This module focuses exclusively on the <strong>ESP32</strong> board.
	</p>
</section>

<!-- Sign In -->
<section id="sign-in" class="mb-12">
	<h2 class="text-2xl font-bold mb-4">Creating an Account</h2>
	<p>
		Before proceeding, the first step is to <strong>Sign In / Sign Up</strong>, located in the top-right corner. 
		To access all Wokwi features, signing in is essential. You can use Google, GitHub, or email — with Google being the easiest option.
	</p>
	<img src="/images/Pasted_image_20250919141933.png" alt="Login options on Wokwi" class="my-4 border rounded-lg shadow w-full" />
	<p>
		After logging in, the "Sign In" button will be replaced by your profile icon. Click it to access features like <strong>My Projects</strong> — where you save and manage your projects.
	</p>
	<img src="/images/Pasted_image_20250920060340.png" alt="Profile menu after login" class="my-4 border rounded-lg shadow w-full" />
</section>

<!-- ESP32 Board -->
<section id="esp32-template" class="mb-12">
	<h2 class="text-2xl font-bold mb-4">Using ESP32 in Wokwi</h2>
	<p>
		Navigate to the ESP32 section. Here, you’ll find four sub-sections: <em>Featured Projects</em>, <em>Starter Template</em>, <em>ESP-IDF Template</em>, and <em>Latest Projects</em>. 
		This module uses the <strong>Starter Template</strong> because its code is simpler and easier to understand than the ESP-IDF version.
	</p>
	<img src="/images/Pasted_image_20250920060711.png" alt="Starter Template selection" class="my-4 border rounded-lg shadow w-full" />
	<p>
		There are many boards in the starter template, but we’ll focus only on the standard ESP32.
	</p>
	<img src="/images/Pasted_image_20250920060914.png" alt="ESP32 Starter Template" class="my-4 border rounded-lg shadow w-full" />
	<p>The editor displays two main functions:</p>
	<ul class="list-disc ml-6 my-2">
		<li><code class="bg-gray-200 px-1 rounded">void setup()</code>: runs once when the program starts.</li>
		<li><code class="bg-gray-200 px-1 rounded">void loop()</code>: runs continuously in a loop.</li>
	</ul>
	<img src="/images/Pasted_image_20250920074303.png" alt="Arduino code structure in Wokwi" class="my-4 border rounded-lg shadow w-full" />
</section>

<!-- Initial Page -->
<section id="initial-page" class="mb-12">
	<h2 class="text-2xl font-bold mb-4">Editor Interface</h2>
	<p>
		The ESP32 editor shows both the code and a visual simulation of the board. The code file is known as <code>sketch.ino</code>. 
		The visual representation allows GUI-based editing, but you can also edit connections directly via the <code>diagram.json</code> tab if preferred.
	</p>
	<Note type="info">
		The functions <code>setup()</code> and <code>loop()</code> are essential. Removing either will cause an error during simulation.
	</Note>
	<img src="/images/Pasted_image_20250920074303.png" alt="Initial editor view" class="my-4 border rounded-lg shadow w-full" />
</section>

<!-- Adding Components -->
<section id="add-components" class="mb-12">
	<h2 class="text-2xl font-bold mb-4">Adding Components</h2>
	<p>
		Use the <strong>+</strong> button to open the component library. Wokwi offers a wide range of components including LEDs, push buttons, resistors, RGB LEDs, OLEDs, LCDs, and more.
	</p>
	<img src="/images/Pasted_image_20250922091138.png" alt="Add component button" class="my-4 border rounded-lg shadow w-full" />
	<p>
		Since the library contains many sensors and displays, finding specific components can be overwhelming. 
		Wokwi provides a <strong>search feature</strong> — simply type the component name in the search bar.
	</p>
	<img src="/images/Pasted_image_20250922091800.png" alt="Component search feature" class="my-4 border rounded-lg shadow w-full" />
</section>

<!-- Connecting Components -->
<section id="connect-components" class="mb-12">
	<h2 class="text-2xl font-bold mb-4">Connecting Components</h2>
	<p>
		Connecting components in Wokwi is simple — just click on the glowing connection points. 
		Add an LED from the component library. Connect the <strong>Anode (A)</strong> to <strong>Pin 26</strong> on the ESP32, and the <strong>Cathode (C)</strong> to <strong>GND</strong>.
	</p>
	<img src="/images/Pasted_image_20250922104850.png" alt="LED connected to ESP32" class="my-4 border rounded-lg shadow w-full" />
	<Note type="info">A = Anode, C = Cathode.</Note>
</section>

<!-- Writing Code -->
<section id="coding" class="mb-12">
	<h2 class="text-2xl font-bold mb-4">Writing Code in the Text Editor</h2>
	<p>
		Since this project only lights up one LED using the ESP32, we’ll replace the default code with a simpler version:
	</p>

	<CodeBlock code={`
void setup() {
  pinMode(26, OUTPUT);
  digitalWrite(26, HIGH);
}

void loop() {
  delay(10);
}`}/>

	<p><strong>Explanation:</strong></p>
	<ul class="list-disc ml-6 my-2 space-y-1">
		<li><code class="bg-gray-200 px-1 rounded">pinMode(26, OUTPUT)</code>: Configures Pin 26 as an output.</li>
		<li><code class="bg-gray-200 px-1 rounded">digitalWrite(26, HIGH)</code>: Sets Pin 26 to HIGH (on), turning the LED on.</li>
	</ul>
	<p>This code initializes the pin and keeps the LED lit indefinitely with minimal delay.</p>
	<img src="/images/Pasted_image_20250922111718.png" alt="Code in Wokwi editor" class="my-4 border rounded-lg shadow w-full" />
</section>

<!-- Running Simulation -->
<section id="run-simulation" class="mb-12">
	<h2 class="text-2xl font-bold mb-4">Running the Simulation</h2>
	<p>
		Once the circuit is complete and the code is written, the simulation is ready to run. 
		In Wokwi, simply click the green <strong>Play</strong> button. If there are no code errors, the simulation starts immediately.
	</p>
	<img src="/images/Pasted_image_20250922091138.png" alt="Play button in Wokwi" class="my-4 border rounded-lg shadow w-full" />
	<Note type="warning">
		A "Server Error" may occasionally appear due to high server load. If so, try refreshing or consider upgrading to Wokwi Premium for uninterrupted access.
	</Note>

	<!-- Embedded Simulation -->
	<EmbeddedSimulation src="https://wokwi.com/projects/392792918005518336" />
</section>
</main>
	
</div>