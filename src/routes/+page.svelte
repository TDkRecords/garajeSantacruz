<script>
    let images = "/src/lib/images/default.webp";

    // Datos del blog
    let blogPosts = [
        {
            id: 1,
            title: "Mantenimiento Preventivo: La Clave para una Mayor Durabilidad",
            excerpt:
                "Descubre por qué el mantenimiento preventivo es esencial para alargar la vida útil de tu vehículo y evitar costosas reparaciones.",
            description:
                "El mantenimiento preventivo es una de las mejores inversiones que puedes hacer para tu vehículo. Consiste en realizar revisiones periódicas y cambios de fluidos, filtros y piezas antes de que se produzcan fallos mayores. En Garaje Santacruz, recomendamos realizar mantenimiento preventivo cada 5,000 km o cada 6 meses, lo que ocurra primero. Esto incluye cambio de aceite, revisión de frenos, suspensión, batería, neumáticos y sistemas eléctricos. Nuestros técnicos certificados utilizan las mejores herramientas y productos para garantizar que tu vehículo funcione en óptimas condiciones.",
            image: images,
            date: "15 Octubre, 2024",
            category: "Mantenimiento",
        },
        {
            id: 2,
            title: "Señales de que tu Motor Necesita Atención",
            excerpt:
                "Aprende a identificar las señales tempranas de problemas en el motor antes de que se conviertan en reparaciones mayores.",
            description:
                "El motor es el corazón de tu vehículo, y detectar problemas tempranos puede ahorrarte miles en reparaciones. Algunas señales de alerta incluyen: humo excesivo del escape, pérdida de potencia, ruidos extraños, sobrecalentamiento, consumo excesivo de aceite o combustible, y dificultad para arrancar. Si notas cualquiera de estos síntomas, es importante traer tu vehículo inmediatamente a Garaje Santacruz para un diagnóstico profesional. Nuestros técnicos utilizan equipo de diagnóstico computarizado de última generación para identificar y solucionar problemas de manera precisa y eficiente.",
            image: images,
            date: "8 Octubre, 2024",
            category: "Diagnóstico",
        },
        {
            id: 3,
            title: "Cómo Cuidar tu Sistema de Frenos",
            excerpt:
                "Consejos prácticos para mantener tu sistema de frenos en perfectas condiciones y garantizar tu seguridad en la carretera.",
            description:
                "Los frenos son uno de los sistemas más críticos para la seguridad de tu vehículo. Para mantenerlos en óptimas condiciones, es importante revisar el nivel de líquido de frenos mensualmente, escuchar ruidos inusuales como chirridos o rechinidos, prestar atención a vibraciones en el pedal, y realizar inspecciones profesionales cada 10,000 km. También es crucial reemplazar las pastillas de freno cuando el grosor sea menor a 3mm. En Garaje Santacruz, utilizamos pastillas de freno de alta calidad y realizamos ajustes precisos para garantizar un frenado óptimo y seguro.",
            image: images,
            date: "1 Octubre, 2024",
            category: "Seguridad",
        },
    ];

    // Estado del off-canvas
    let isOffcanvasOpen = false;
    let selectedArticle = null;

    // Funciones para controlar el off-canvas
    function openOffcanvas(article) {
        selectedArticle = article;
        isOffcanvasOpen = true;
        document.body.style.overflow = "hidden"; // Prevenir scroll cuando está abierto
    }

    function closeOffcanvas() {
        isOffcanvasOpen = false;
        // Pequeño delay para permitir que la animación se complete antes de restaurar el artículo seleccionado
        setTimeout(() => {
            selectedArticle = null;
            document.body.style.overflow = "auto"; // Restaurar scroll
        }, 300); // Coincide con la duración de la animación (300ms)
    }
</script>

<svelte:head>
    <title>Garaje Santacruz - Taller Mecánico Profesional</title>
    <meta
        name="description"
        content="Garaje Santacruz - Servicios profesionales de mecánica automotriz, mantenimiento y reparación de vehículos."
    />
    <meta
        name="keywords"
        content="garaje, taller mecánico, mecánica automotriz, reparación vehículos, mantenimiento"
    />
    <meta name="author" content="Garaje Santa Cruz" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

<!-- Hero Section -->
<section class="bg-white min-h-screen flex items-center">
    <div
        class="container mx-auto px-6 lg:px-12 py-16 flex flex-col lg:flex-row items-center lg:items-center gap-12"
    >
        <!-- Imagen circular -->
        <div class="flex-1 flex justify-center lg:justify-end">
            <div
                class="w-56 h-56 md:w-72 md:h-72 lg:w-96 lg:h-96 rounded-full overflow-hidden shadow-lg border-4 border-red-600"
            >
                <img
                    src={images}
                    alt="Garaje Santa Cruz - Taller Mecánico"
                    class="w-full h-full object-cover"
                />
            </div>
        </div>

        <!-- Texto -->
        <div class="flex-1 text-center lg:text-left">
            <h1
                class="text-5xl md:text-6xl lg:text-7xl font-bold text-black leading-tight mb-6"
            >
                GARAJE <span class="text-red-600 block">SANTACRUZ</span>
            </h1>
            <div
                class="flex flex-col md:flex-row gap-4 justify-center lg:justify-start"
            >
                <button
                    class="bg-red-600 hover:bg-red-700 text-white font-bold py-4 px-8 rounded-lg text-lg transition-colors"
                >
                    <i class="fa-solid fa-wrench mr-2"></i>Solicitar Servicio
                </button>
                <button
                    class="border-2 border-black text-black hover:bg-black hover:text-white font-bold py-4 px-8 rounded-lg text-lg transition-colors"
                >
                    <i class="fa-solid fa-list mr-2"></i>Ver Servicios
                </button>
            </div>
        </div>
    </div>
</section>

<!-- Servicios Section -->
<section class="bg-gray-50 py-16">
    <div class="container mx-auto px-4">
        <div class="text-center mb-12">
            <h2 class="text-4xl md:text-5xl font-bold text-black mb-4">
                NUESTROS <span class="text-red-600">SERVICIOS</span>
            </h2>
            <p class="text-xl text-gray-600 max-w-3xl mx-auto">
                Ofrecemos una amplia gama de servicios mecánicos para mantener
                tu vehículo en perfectas condiciones.
            </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Servicio 1 -->
            <div
                class="bg-white p-8 rounded-lg shadow-lg hover:shadow-xl transition-shadow"
            >
                <div
                    class="w-16 h-16 bg-red-600 rounded-full flex items-center justify-center mb-6 mx-auto"
                >
                    <i class="fa-solid fa-bolt text-white"></i>
                </div>
                <h3 class="text-xl font-bold text-black mb-4 text-center">
                    Mantenimiento General
                </h3>
                <p class="text-gray-600 text-center">
                    Servicios completos de mantenimiento preventivo para alargar
                    la vida útil de tu vehículo.
                </p>
            </div>

            <!-- Servicio 2 -->
            <div
                class="bg-white p-8 rounded-lg shadow-lg hover:shadow-xl transition-shadow"
            >
                <div
                    class="w-16 h-16 bg-red-600 rounded-full flex items-center justify-center mb-6 mx-auto"
                >
                    <i class="fa-solid fa-check-circle text-white"></i>
                </div>
                <h3 class="text-xl font-bold text-black mb-4 text-center">
                    Reparación de Motor
                </h3>
                <p class="text-gray-600 text-center">
                    Diagnóstico y reparación especializada de motores a gasolina
                    y diésel.
                </p>
            </div>

            <!-- Servicio 3 -->
            <div
                class="bg-white p-8 rounded-lg shadow-lg hover:shadow-xl transition-shadow"
            >
                <div
                    class="w-16 h-16 bg-red-600 rounded-full flex items-center justify-center mb-6 mx-auto"
                >
                    <i class="fa-solid fa-wrench text-white"></i>
                </div>
                <h3 class="text-xl font-bold text-black mb-4 text-center">
                    Sistema Eléctrico
                </h3>
                <p class="text-gray-600 text-center">
                    Reparación y mantenimiento de sistemas eléctricos y
                    electrónicos del vehículo.
                </p>
            </div>

            <!-- Servicio 4 -->
            <div
                class="bg-white p-8 rounded-lg shadow-lg hover:shadow-xl transition-shadow"
            >
                <div
                    class="w-16 h-16 bg-red-600 rounded-full flex items-center justify-center mb-6 mx-auto"
                >
                    <i class="fa-solid fa-clipboard-check text-white"></i>
                </div>
                <h3 class="text-xl font-bold text-black mb-4 text-center">
                    Frenos y Suspensión
                </h3>
                <p class="text-gray-600 text-center">
                    Servicio especializado en sistemas de frenos y suspensión
                    para mayor seguridad.
                </p>
            </div>

            <!-- Servicio 5 -->
            <div
                class="bg-white p-8 rounded-lg shadow-lg hover:shadow-xl transition-shadow"
            >
                <div
                    class="w-16 h-16 bg-red-600 rounded-full flex items-center justify-center mb-6 mx-auto"
                >
                    <i class="fa-solid fa-lightbulb text-white"></i>
                </div>
                <h3 class="text-xl font-bold text-black mb-4 text-center">
                    Aire Acondicionado
                </h3>
                <p class="text-gray-600 text-center">
                    Mantenimiento y reparación de sistemas de climatización para
                    tu confort.
                </p>
            </div>

            <!-- Servicio 6 -->
            <div
                class="bg-white p-8 rounded-lg shadow-lg hover:shadow-xl transition-shadow"
            >
                <div
                    class="w-16 h-16 bg-red-600 rounded-full flex items-center justify-center mb-6 mx-auto"
                >
                    <i class="fa-solid fa-chart-bar text-white"></i>
                </div>
                <h3 class="text-xl font-bold text-black mb-4 text-center">
                    Diagnóstico Computarizado
                </h3>
                <p class="text-gray-600 text-center">
                    Tecnología de punta para diagnóstico preciso de problemas
                    electrónicos.
                </p>
            </div>
        </div>
    </div>
</section>

<!-- Sobre Nosotros Section -->
<section class="bg-white py-16">
    <div class="container mx-auto px-4">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
            <!-- Espacio para imagen del taller -->
            <div class="order-2 lg:order-1">
                <div
                    class="bg-gray-200 rounded-lg aspect-video flex items-center justify-center text-gray-500 text-lg"
                >
                    <!-- Reemplaza esta URL con una imagen del interior del taller -->
                    <img
                        src={images}
                        alt="Interior del Garaje Santacruz"
                        class="w-full h-full object-cover rounded-lg"
                    />
                </div>
            </div>

            <!-- Contenido de texto -->
            <div class="order-1 lg:order-2">
                <h2 class="text-4xl md:text-5xl font-bold text-black mb-6">
                    SOBRE <span class="text-red-600">GARAJE SANTACRUZ</span>
                </h2>
                <p class="text-lg text-gray-700 mb-6">
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                    Eveniet facilis, possimus harum sed laborum consectetur
                </p>
            </div>
        </div>
    </div>
</section>

<!-- Certificaciones Section -->
<section class="bg-gray-50 py-16">
    <div class="container mx-auto px-4">
        <div class="text-center mb-12">
            <h2 class="text-4xl md:text-5xl font-bold text-black mb-4">
                CERTIFICACIONES Y <span class="text-red-600"
                    >RECONOCIMIENTOS</span
                >
            </h2>
        </div>

        <div
            class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-8 items-center"
        >
            <div class="bg-white p-6 rounded-lg shadow-lg text-center">
                <div
                    class="w-16 h-16 bg-red-600 rounded-full flex items-center justify-center mx-auto mb-4"
                >
                    <i class="fa-solid fa-check-circle text-white"></i>
                </div>
                <h3 class="font-bold text-black">CERTIFICACIÓN 1</h3>
            </div>

            <div class="bg-white p-6 rounded-lg shadow-lg text-center">
                <div
                    class="w-16 h-16 bg-red-600 rounded-full flex items-center justify-center mx-auto mb-4"
                >
                    <i class="fa-solid fa-bolt text-white"></i>
                </div>
                <h3 class="font-bold text-black">CERTIFICACIÓN 2</h3>
            </div>

            <div class="bg-white p-6 rounded-lg shadow-lg text-center">
                <div
                    class="w-16 h-16 bg-red-600 rounded-full flex items-center justify-center mx-auto mb-4"
                >
                    <i class="fa-solid fa-building text-white"></i>
                </div>
                <h3 class="font-bold text-black">CERTIFICACIÓN 3</h3>
            </div>

            <div class="bg-white p-6 rounded-lg shadow-lg text-center">
                <div
                    class="w-16 h-16 bg-red-600 rounded-full flex items-center justify-center mx-auto mb-4"
                >
                    <i class="fa-solid fa-dollar-sign text-white"></i>
                </div>
                <h3 class="font-bold text-black">CERTIFICACIÓN 4</h3>
            </div>

            <div class="bg-white p-6 rounded-lg shadow-lg text-center">
                <div
                    class="w-16 h-16 bg-red-600 rounded-full flex items-center justify-center mx-auto mb-4"
                >
                    <i class="fa-solid fa-award text-white"></i>
                </div>
                <h3 class="font-bold text-black">CERTIFICACIÓN 5</h3>
            </div>
        </div>
    </div>
</section>

<!-- Promociones Section -->
<section class="bg-red-600 py-16">
    <div class="container mx-auto px-4 text-center">
        <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">
            <i class="fas fa-star text-white mr-2"></i>PROMOCIONES
            <span class="text-black">ESPECIALES</span>
        </h2>
        <p class="text-xl text-white mb-8 max-w-3xl mx-auto">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua.
        </p>

        <div
            class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 max-w-6xl mx-auto"
        >
            <div class="bg-white p-8 rounded-lg">
                <i class="fas fa-gift text-red-600 mr-3"></i>
                <p class="text-gray-700 mb-4">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                </p>
                <div class="text-2xl font-bold text-red-600 mb-4">50% OFF</div>
                <button
                    class="bg-red-600 hover:bg-red-700 text-white font-bold py-2 px-6 rounded-lg"
                    >OBTENER OFERTA</button
                >
            </div>

            <div class="bg-white p-8 rounded-lg">
                <i class="fas fa-gift text-red-600 mr-3"></i>
                <p class="text-gray-700 mb-4">
                    Ut enim ad minim veniam, quis nostrud exercitation ullamco.
                </p>
                <div class="text-2xl font-bold text-red-600 mb-4">30% OFF</div>
                <button
                    class="bg-red-600 hover:bg-red-700 text-white font-bold py-2 px-6 rounded-lg"
                    >OBTENER OFERTA</button
                >
            </div>

            <div class="bg-white p-8 rounded-lg">
                <i class="fas fa-gift text-red-600 mr-3"></i>
                <p class="text-gray-700 mb-4">
                    Duis aute irure dolor in reprehenderit in voluptate velit.
                </p>
                <div class="text-2xl font-bold text-red-600 mb-4">2x1</div>
                <button
                    class="bg-red-600 hover:bg-red-700 text-white font-bold py-2 px-6 rounded-lg"
                    >OBTENER OFERTA</button
                >
            </div>
        </div>
    </div>
</section>

<!-- Blog Section -->
<section class="bg-gray-50 py-16">
    <div class="container mx-auto px-4">
        <div class="text-center mb-12">
            <h2 class="text-4xl md:text-5xl font-bold text-black mb-4">
                NOTICIAS Y <span class="text-red-600">CONSEJOS</span>
            </h2>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            {#each blogPosts as post}
                <article
                    class="bg-white rounded-lg shadow-lg overflow-hidden hover:shadow-xl transition-shadow"
                >
                    <div class="relative h-48 overflow-hidden">
                        <img
                            src={post.image}
                            alt={post.title}
                            class="w-full h-full object-cover transition-transform hover:scale-105"
                        />
                        <div class="absolute top-4 left-4">
                            <span
                                class="bg-red-600 text-white text-sm font-bold px-3 py-1 rounded-full"
                            >
                                {post.category}
                            </span>
                        </div>
                    </div>
                    <div class="p-6">
                        <h3
                            class="text-xl font-bold text-black mb-3 line-clamp-2"
                        >
                            {post.title}
                        </h3>
                        <p class="text-gray-600 mb-4 line-clamp-3">
                            {post.excerpt}
                        </p>
                        <div class="flex items-center justify-between">
                            <span class="text-sm text-gray-500"
                                >{post.date}</span
                            >
                            <button
                                class="bg-red-600 hover:bg-red-700 text-white font-bold py-2 px-4 rounded-lg transition-colors flex items-center gap-2"
                                on:click={() => openOffcanvas(post)}
                            >
                                <i
                                    class="fa-solid fa-arrow-right text-white ml-2"
                                ></i>
                            </button>
                        </div>
                    </div>
                </article>
            {/each}
        </div>
    </div>
</section>

<!-- Off-Canvas para artículos del blog -->
{#if isOffcanvasOpen && selectedArticle}
    <div class="fixed inset-0 z-50 overflow-hidden">
        <!-- Overlay -->
        <div
            class="absolute inset-0 bg-black/50 transition-opacity duration-300 ease-in-out"
            class:bg-opacity-50={isOffcanvasOpen}
            class:bg-opacity-0={!isOffcanvasOpen}
            on:click={closeOffcanvas}
        ></div>

        <!-- Panel del off-canvas -->
        <div
            class="absolute left-0 top-0 h-full w-full sm:max-w-md md:max-w-lg lg:max-w-xl xl:max-w-2xl bg-white shadow-xl transform transition-all duration-300 ease-in-out"
            class:translate-x-0={isOffcanvasOpen}
            class:opacity-100={isOffcanvasOpen}
            class:-translate-x-full={!isOffcanvasOpen}
            class:opacity-0={!isOffcanvasOpen}
        >
            <!-- Header del off-canvas -->
            <div class="flex items-center justify-between p-6 border-b">
                <h2 class="text-2xl font-bold text-black">Artículo</h2>
                <button
                    class="p-2 hover:bg-gray-100 rounded-full transition-colors"
                    on:click={closeOffcanvas}
                >
                    <i class="fa-solid fa-times"></i>
                </button>
            </div>

            <!-- Contenido del artículo -->
            <div class="p-6 overflow-y-auto h-full pb-20">
                <!-- Imagen -->
                <div class="mb-6">
                    <img
                        src={selectedArticle.image}
                        alt={selectedArticle.title}
                        class="w-full h-64 object-cover rounded-lg"
                    />
                </div>

                <!-- Información del artículo -->
                <div class="space-y-4">
                    <!-- Categoría y fecha -->
                    <div class="flex items-center gap-4 text-sm text-gray-600">
                        <span
                            class="bg-red-600 text-white px-3 py-1 rounded-full font-bold"
                        >
                            {selectedArticle.category}
                        </span>
                        <span>{selectedArticle.date}</span>
                    </div>

                    <!-- Título -->
                    <h3 class="text-3xl font-bold text-black leading-tight">
                        {selectedArticle.title}
                    </h3>

                    <!-- Descripción -->
                    <div class="prose prose-lg max-w-none">
                        <p
                            class="text-gray-700 leading-relaxed whitespace-pre-line"
                        >
                            {selectedArticle.description}
                        </p>
                    </div>

                    <!-- Botón de acción -->
                    <div class="pt-6 mb-7">
                        <button
                            class="w-full bg-red-600 hover:bg-red-700 text-white font-bold py-4 px-6 rounded-lg transition-colors"
                        >
                            Solicitar Información
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>
{/if}

<!-- Testimonios Section
<section class="bg-white py-16">
    <div class="container mx-auto px-4">
        <div class="text-center mb-12">
            <h2 class="text-4xl md:text-5xl font-bold text-black mb-4">
                TESTIMONIOS <span class="text-red-600">DE CLIENTES</span>
            </h2>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <div class="bg-gray-50 p-8 rounded-lg">
                <div class="flex items-center mb-4">
                    <div class="w-12 h-12 bg-red-600 rounded-full flex items-center justify-center text-white font-bold text-lg">J</div>
                    <div class="ml-4">
                        <h4 class="font-bold text-black">TESTIMONIO 1</h4>
                        <p class="text-gray-600">Cliente Satisfecho</p>
                    </div>
                </div>
                <p class="text-gray-700">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
            </div>

            <div class="bg-gray-50 p-8 rounded-lg">
                <div class="flex items-center mb-4">
                    <div class="w-12 h-12 bg-red-600 rounded-full flex items-center justify-center text-white font-bold text-lg">M</div>
                    <div class="ml-4">
                        <h4 class="font-bold text-black">TESTIMONIO 2</h4>
                        <p class="text-gray-600">Cliente Recurrente</p>
                    </div>
                </div>
                <p class="text-gray-700">Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
            </div>

            <div class="bg-gray-50 p-8 rounded-lg">
                <div class="flex items-center mb-4">
                    <div class="w-12 h-12 bg-red-600 rounded-full flex items-center justify-center text-white font-bold text-lg">C</div>
                    <div class="ml-4">
                        <h4 class="font-bold text-black">TESTIMONIO 3</h4>
                        <p class="text-gray-600">Cliente Empresarial</p>
                    </div>
                </div>
                <p class="text-gray-700">Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
            </div>
        </div>
    </div>
</section> -->

<!-- Galería Section -->
<section class="bg-gray-50 py-16">
    <div class="container mx-auto px-4">
        <div class="text-center mb-12">
            <h2 class="text-4xl md:text-5xl font-bold text-black mb-4">
                <i class="fas fa-images text-red-600 mr-3"></i>GALERÍA DE
                <span class="text-red-600">TRABAJOS</span>
            </h2>
        </div>

        <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
            <div
                class="bg-gray-200 rounded-lg aspect-square flex items-center justify-center text-gray-500"
            >
                <img
                    src={images}
                    alt="Imagen 1"
                    class="w-full h-full object-cover rounded-lg"
                />
            </div>
            <div
                class="bg-gray-200 rounded-lg aspect-square flex items-center justify-center text-gray-500"
            >
                <img
                    src={images}
                    alt="Imagen 2"
                    class="w-full h-full object-cover rounded-lg"
                />
            </div>
            <div
                class="bg-gray-200 rounded-lg aspect-square flex items-center justify-center text-gray-500"
            >
                <img
                    src={images}
                    alt="Imagen 3"
                    class="w-full h-full object-cover rounded-lg"
                />
            </div>
            <div
                class="bg-gray-200 rounded-lg aspect-square flex items-center justify-center text-gray-500"
            >
                <img
                    src={images}
                    alt="Imagen 4"
                    class="w-full h-full object-cover rounded-lg"
                />
            </div>
            <div
                class="bg-gray-200 rounded-lg aspect-square flex items-center justify-center text-gray-500"
            >
                <img
                    src={images}
                    alt="Imagen 5"
                    class="w-full h-full object-cover rounded-lg"
                />
            </div>
            <div
                class="bg-gray-200 rounded-lg aspect-square flex items-center justify-center text-gray-500"
            >
                <img
                    src={images}
                    alt="Imagen 6"
                    class="w-full h-full object-cover rounded-lg"
                />
            </div>
            <div
                class="bg-gray-200 rounded-lg aspect-square flex items-center justify-center text-gray-500"
            >
                <img
                    src={images}
                    alt="Imagen 7"
                    class="w-full h-full object-cover rounded-lg"
                />
            </div>
            <div
                class="bg-gray-200 rounded-lg aspect-square flex items-center justify-center text-gray-500"
            >
                <img
                    src={images}
                    alt="Imagen 8"
                    class="w-full h-full object-cover rounded-lg"
                />
            </div>
        </div>
    </div>
</section>

<!-- Ubicación Section -->
<section class="bg-white py-16">
    <div class="container mx-auto px-4">
        <div class="text-center mb-12">
            <h2 class="text-4xl md:text-5xl font-bold text-black mb-4">
                NUESTRA <span class="text-red-600">UBICACIÓN</span>
            </h2>
        </div>

        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
            <div>
                <div
                    class="bg-gray-200 rounded-lg aspect-video flex items-center justify-center text-gray-500 text-lg mb-6"
                >
                    <iframe
                        src="https://www.google.com/maps/embed?pb=!1m17!1m12!1m3!1d3988.935486282809!2d-77.28178692614765!3d1.2053373620256551!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m2!1m1!2zMcKwMTInMTkuMiJOIDc3wrAxNic0NS4yIlc!5e0!3m2!1ses-419!2sco!4v1760206962787!5m2!1ses-419!2sco"
                        width="600"
                        height="450"
                        style="border:0;"
                        allowfullscreen=""
                        loading="lazy"
                        referrerpolicy="no-referrer-when-downgrade"
                    ></iframe>
                </div>
            </div>

            <div>
                <i class="fas fa-users text-red-600 mr-3"></i>
                <div class="space-y-4 text-gray-700">
                    <p>
                        <strong>Dirección:</strong> Lorem ipsum dolor sit amet, consectetur
                        adipiscing elit.
                    </p>
                    <p>
                        <strong>Teléfono:</strong> Lorem ipsum dolor sit amet, consectetur
                        adipiscing elit.
                    </p>
                    <p>
                        <strong>Email:</strong> Lorem ipsum dolor sit amet, consectetur
                        adipiscing elit.
                    </p>
                    <p>
                        <strong>Horario:</strong> Lorem ipsum dolor sit amet, consectetur
                        adipiscing elit.
                    </p>
                </div>

                <div class="mt-8">
                    <h4 class="text-lg font-bold text-black mb-3">
                        Indicaciones:
                    </h4>
                    <p class="text-gray-700">
                        Sed do eiusmod tempor incididunt ut labore et dolore
                        magna aliqua. Ut enim ad minim veniam, quis nostrud
                        exercitation ullamco laboris nisi ut aliquip ex ea
                        commodo consequat.
                    </p>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- Contacto Section -->
<section class="bg-gray-50 py-16">
    <div class="container mx-auto px-4">
        <div class="text-center mb-12">
            <h2 class="text-4xl md:text-5xl font-bold text-black mb-4">
                CONTÁCTANOS
            </h2>
            <p class="text-xl text-gray-600">
                ¿Necesitas nuestros servicios? ¡Estamos aquí para ayudarte!
            </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-4xl mx-auto">
            <!-- Teléfono -->
            <div class="bg-white p-8 rounded-lg shadow-lg text-center">
                <div
                    class="w-16 h-16 bg-red-600 rounded-full flex items-center justify-center mb-6 mx-auto"
                >
                    <i class="fa-solid fa-phone text-white"></i>
                </div>
                <h3 class="text-xl font-bold text-black mb-4">Teléfono</h3>
                <p class="text-gray-600 mb-2">(555) 123-4567</p>
                <p class="text-gray-600">(555) 987-6543</p>
            </div>

            <!-- Dirección -->
            <div class="bg-white p-8 rounded-lg shadow-lg text-center">
                <div
                    class="w-16 h-16 bg-red-600 rounded-full flex items-center justify-center mb-6 mx-auto"
                >
                    <i class="fa-solid fa-map-marker-alt text-white"></i>
                </div>
                <h3 class="text-xl font-bold text-black mb-4">Dirección</h3>
                <p class="text-gray-600">Calle Principal 123</p>
                <p class="text-gray-600">Santa Cruz, Bolivia</p>
            </div>

            <!-- Horario -->
            <div class="bg-white p-8 rounded-lg shadow-lg text-center">
                <div
                    class="w-16 h-16 bg-red-600 rounded-full flex items-center justify-center mb-6 mx-auto"
                >
                    <i class="fa-solid fa-clock text-white"></i>
                </div>
                <h3 class="text-xl font-bold text-black mb-4">Horario</h3>
                <p class="text-gray-600 mb-2">Lunes - Viernes</p>
                <p class="text-gray-600 mb-2">8:00 AM - 6:00 PM</p>
                <p class="text-gray-600">Sábado: 8:00 AM - 2:00 PM</p>
            </div>
        </div>
    </div>
</section>

<!-- Preguntas Frecuentes Section -->
<section class="bg-white py-16">
    <div class="container mx-auto px-4">
        <div class="text-center mb-12">
            <h2 class="text-4xl md:text-5xl font-bold text-black mb-4">
                PREGUNTAS <span class="text-red-600">FRECUENTES</span>
            </h2>
        </div>

        <div class="max-w-4xl mx-auto space-y-6">
            <div class="bg-gray-50 p-6 rounded-lg">
                <h3>
                    <i class="fa-solid fa-question-circle text-red-600 mr-3"
                    ></i>
                    ¿Cuánto tiempo toma un servicio de mantenimiento?
                </h3>
                <p class="text-gray-700">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed
                    do eiusmod tempor incididunt ut labore et dolore magna
                    aliqua. Ut enim ad minim veniam.
                </p>
            </div>

            <div class="bg-gray-50 p-6 rounded-lg">
                <h3>
                    <i class="fa-solid fa-question-circle text-red-600 mr-3"
                    ></i>
                    ¿Ofrecen garantía en sus servicios?
                </h3>
                <p class="text-gray-700">
                    Quis nostrud exercitation ullamco laboris nisi ut aliquip ex
                    ea commodo consequat. Duis aute irure dolor in reprehenderit
                    in voluptate velit esse.
                </p>
            </div>

            <div class="bg-gray-50 p-6 rounded-lg">
                <h3>
                    <i class="fa-solid fa-question-circle text-red-600 mr-3"
                    ></i>
                    ¿Trabajan con todas las marcas de vehículos?
                </h3>
                <p class="text-gray-700">
                    Cillum dolore eu fugiat nulla pariatur. Excepteur sint
                    occaecat cupidatat non proident, sunt in culpa qui officia
                    deserunt mollit anim id est laborum.
                </p>
            </div>

            <div class="bg-gray-50 p-6 rounded-lg">
                <h3>
                    <i class="fa-solid fa-question-circle text-red-600 mr-3"
                    ></i>
                    ¿Necesito agendar una cita previa?
                </h3>
                <p class="text-gray-700">
                    Sed ut perspiciatis unde omnis iste natus error sit
                    voluptatem accusantium doloremque laudantium, totam rem
                    aperiam.
                </p>
            </div>
        </div>
    </div>
</section>
