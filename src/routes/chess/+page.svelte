<script>
	let toplamSaniye = 10;

	let dakika = Math.floor(toplamSaniye / 60);
	let saniye = toplamSaniye % 60;

	// @ts-ignore
	function herSaniyeÇalışanFonksiyon() {
		if (toplamSaniye > 0) {
			toplamSaniye -= 1;
			// @ts-ignore
			dakika = Math.floor(toplamSaniye / 60);
			saniye = toplamSaniye % 60;
		}
	}

	function sayaçBaşlatıcı() {
		setInterval(herSaniyeÇalışanFonksiyon, 1000);
	}

	// @ts-ignore
	function sıfırEkleyen(sayı) {
		if (sayı < 10) {
			return "0" + sayı;
		}
		return sayı;
	}
</script>

<div class="flex flex-col gap-20 justify-center items-center h-full">
	{#if saniye === 0}
		<h1 class="text-6xl text-red-600">SÜREN BİTTİ OÇ</h1>
	{/if}

	<p class="text-9xl">{sıfırEkleyen(dakika)}:{sıfırEkleyen(saniye)}</p>
	<button on:click={sayaçBaşlatıcı}> Başlat </button>
</div>
