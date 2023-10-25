Documentación de Proyecto Astro y GSAP
Resumen
Este proyecto utiliza Astro para crear una aplicación web y GSAP para animaciones. El proyecto consta de tres archivos principales: layout.astro, index.astro, y herosection.astro. El código se utiliza para crear una página de inicio con animaciones de entrada.

Archivos Principales
layout.astro
astro
Copy code
---
import Navbar from '../components/Navbar.astro';
interface Props {
	title: string;
}

const { title } = Astro.props;
---

<!doctype html>
<html lang="en">
	<head>
		<!-- ... -->
	</head>
	<body>
		<Navbar />
		<slot />
	</body>
</html>
<style is:global>
	<!-- Estilos globales -->
</style>
layout.astro define la estructura básica de la página, incluyendo la barra de navegación y los estilos globales.
index.astro
astro
Copy code
---
import HeroSection from '../components/HeroSection.astro';
import Layout from '../layouts/Layout.astro';
import '../styles/Preloader.css'
---

<Layout title="Welcome to Astro.">
	<!-- ... -->
</Layout>
<script>
	// Animaciones con GSAP
</script>
index.astro utiliza el Layout definido en layout.astro para estructurar la página de inicio. También incluye animaciones realizadas con GSAP.
herosection.astro
astro
Copy code
---
import '../styles/Hero.css'
---

<section id="main">
    <div id="main-content">
        <div id="text-content">
            <!-- ... -->
        </div>
        <div id "img-wrapper">
            <!-- ... -->
        </div>
    </div>
</section>
herosection.astro contiene la sección de héroe de la página de inicio, incluyendo el texto y las imágenes.
navbar.astro
astro
Copy code
---
import '../styles/navbar.css'
---

<header>
    <div id="nav-container">
        <nav>
            <!-- ... -->
        </nav>
    </div>
</header>
<script>
    import {gsap} from "gsap";
    const link = document.querySelectorAll(".link");

    gsap.from("header",{
        duration: 1,
        y: -100,
        opacity: 0,
        ease: "power2.out"
    })
</script>
navbar.astro define la barra de navegación y las animaciones de entrada con GSAP.
Uso de GSAP
El archivo index.astro utiliza la librería GSAP para realizar animaciones en la página. Aquí tienes una breve descripción de las animaciones:

MainText(): Realiza una animación de cambio de forma en los elementos con la clase .h1.
Intro(): Anima la aparición de elementos con la clase .block.
Intro2(): Realiza una animación de reducción de ancho en elementos con la clase .block.
Outro(): Realiza una animación de reducción de ancho en el contenedor con el id #loader.
SplitText(): Anima la aparición de elementos con la clase .title.
Img(): Anima la aparición de elementos con el id #img-wrapper.
svgspin(): Realiza una animación de rotación continua en el elemento con el id #svg-spin.
Personalización
Puedes personalizar y ampliar este proyecto según tus necesidades. Añade más secciones, estilos y animaciones utilizando Astro y GSAP según tus requisitos específicos.

Esta documentación proporciona una visión general de tu proyecto Astro y GSAP. Si necesitas documentar partes específicas o tienes preguntas adicionales, no dudes en preguntar.
