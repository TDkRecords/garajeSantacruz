<script>
	import "../app.css";
	import favicon from "$lib/assets/favicon.svg";
	import "@fortawesome/fontawesome-free/css/all.min.css";

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

{@render children?.()}

<footer class="bg-black text-white py-8">
	<div class="container mx-auto px-4">
		<div class="text-center mb-6">
			<h3 class="text-2xl font-bold mb-4">
				GARAJE <span class="text-red-600">SANTACRUZ</span>
			</h3>
			<p class="text-gray-400 mb-6">
				Tu taller mecánico de confianza en Pasto, Nariño
			</p>

			<!-- Social Media Icons -->
			<div class="flex justify-center space-x-6 mb-6">
				<a href="#" class="text-gray-400 hover:text-red-600 transition-colors">
					<i class="fab fa-facebook-f text-2xl"></i>
				</a>
				<a href="#" class="text-gray-400 hover:text-red-600 transition-colors">
					<i class="fab fa-instagram text-2xl"></i>
				</a>
				<a href="#" class="text-gray-400 hover:text-red-600 transition-colors">
					<i class="fab fa-whatsapp text-2xl"></i>
				</a>
				<a href="#" class="text-gray-400 hover:text-red-600 transition-colors">
					<i class="fas fa-envelope text-2xl"></i>
				</a>
			</div>
		</div>

		<div class="border-t border-gray-700 pt-4">
			<p class="text-gray-500">© 2025 Garaje Santacruz. Todos los derechos reservados.</p>
		</div>
	</div>
</footer>
