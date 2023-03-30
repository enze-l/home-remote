<script>
	import {
		PUBLIC_TV_ADDRESS,
		PUBLIC_SCANNER_ADDRESS,
		PUBLIC_PRINTER_ADDRESS,
		PUBLIC_SPEAKER_ADDRESS,
		PUBLIC_ROUTER_ADDRESS
	} from '$env/static/public';

	let netflixRedirect = 'https://www.netflix.com/SwitchProfile';

	import Power from 'svelte-material-icons/Power.svelte';
	import Import from 'svelte-material-icons/Import.svelte';
	import Scanner from 'svelte-material-icons/Scanner.svelte';
	import Printer from 'svelte-material-icons/Printer.svelte';
	import Speaker from 'svelte-material-icons/Speaker.svelte';
	import Lan from 'svelte-material-icons/Lan.svelte';
	import Netflix from 'svelte-material-icons/Netflix.svelte';

	let iconSize = 'w-1/2';
	let iconColor = 'gainsboro';

	let padding = 'px-6 py-10';
	let defaultItemStyling = padding + ' md:hover:bg-slate-600';
	let tvItemStyling = padding + ' bg-sky-600 md:hover:bg-sky-500';
	let netflixItemStyling = padding + ' bg-red-600 md:hover:bg-red-500';
	let musicItemStyling = padding + ' bg-green-600 md:hover:bg-green-500';
</script>

<title>Homepage</title>
<body class="md:grid place-content-center md:w-screen md:h-screen bg-slate-500">
	<div class="grid w-screen place-content-center">
		<div class="grid grid-cols-2 md:grid-cols-4 bg-slate-700 max-w-5xl drop-shadow-2xl">
			<button class={tvItemStyling} on:click={() => fetch(PUBLIC_TV_ADDRESS + '/source')}>
				<Import size={iconSize} color={iconColor} />
			</button>

			<button class={tvItemStyling} on:click={() => fetch(PUBLIC_TV_ADDRESS + '/toggle')}>
				<Power size={iconSize} color={iconColor} />
			</button>

			<button class={musicItemStyling} on:click={() => window.open(PUBLIC_SPEAKER_ADDRESS)}>
				<Speaker size={iconSize} color={iconColor} />
			</button>

			<button class={netflixItemStyling} on:click={() => window.open(netflixRedirect)}>
				<Netflix size={iconSize} color={iconColor} />
			</button>

			<button class={defaultItemStyling} on:click={() => window.open(PUBLIC_SCANNER_ADDRESS)}>
				<Scanner size={iconSize} color={iconColor} />
			</button>

			<button class={defaultItemStyling} on:click={() => window.open(PUBLIC_PRINTER_ADDRESS)}>
				<Printer size={iconSize} color={iconColor} />
			</button>

			<button class={defaultItemStyling} on:click={() => window.open(PUBLIC_ROUTER_ADDRESS)}>
				<Lan size={iconSize} color={iconColor} />
			</button>
			<button>
				<img src="/src/resources/qr-code.png" alt="QR-Code" />
			</button>
		</div>
	</div>
</body>
