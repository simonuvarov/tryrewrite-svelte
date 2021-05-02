<script>
	import Button from '../components/Button.svelte';
	import Input from '../components/Input.svelte';
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

<section>
	<form action="#" method="POST" on:submit|preventDefault={handleSubmit}>
		<div class="input-group">
			<Input bind:value={email} />
			<Input bind:value={password} />
		</div>
		<Button>Sign in</Button>
	</form>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		min-height: 100%;
		justify-content: center;
		align-items: center;
	}

	form {
		padding: 24px;
		margin-top: 6rem;
		display: flex;
		flex-direction: column;
		max-width: 384px;
		width: 100%;
	}

	.input-group {
		display: flex;
		flex-direction: column;
	}
</style>
