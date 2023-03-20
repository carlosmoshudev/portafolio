<script lang="ts">
	const Name: string = 'Carlos Soto Pedreira';
	const Title: string = 'Sistemas · Telecomunicaciones · Desarrollo · Ciberseguridad · AV';
	const Description: string = `Hola, me llaman Carlos Moshu.
Apasionado de la tecnología y especialista en la digitalización de espacios físicos y el tratamiento de datos.
Estoy orientado a la mejora de sistemas y procesos, y la integración de experiencias digitales en el mundo real.`;
</script>

<main>
	<!-- Header of my CV -->
	<header>
		<h1>{Name}</h1>
		<h2>{Title}</h2>
		<p>{Description}</p>
	</header>
	<slot />
</main>

<style>
	@import '../global.css';
</style>
