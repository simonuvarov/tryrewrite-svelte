<script>
	import { signin } from '../services/auth.service';

	let email = '';
	let password = '';

	const handleSubmit = () => {
		signin({ email, password })
			.then((r) => {
				console.log(r);
				alert(r.accessToken);
			})
			.catch((e) => alert(e));
	};
</script>

<svelte:head>
	<title>Sign in to your account</title>
</svelte:head>

<form action="#" method="POST" on:submit|preventDefault={handleSubmit}>
	<div>
		<input bind:value={email} />
		<input bind:value={password} />
	</div>
	<button>Sign in</button>
</form>
