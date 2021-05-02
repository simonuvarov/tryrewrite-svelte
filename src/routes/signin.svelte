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
	<article>
		<h2 class="text-left text-2xl font-semibold text-gray-700">Sign in to your account</h2>
		<div class="w-full flex flex-col mx-auto max-w-md mt-8">
			<form action="#" method="POST" on:submit|preventDefault={handleSubmit}>
				<div class="input-group">
					<Input bind:value={email} label="Email" />
					<Input bind:value={password} class="mt-4" label="Password" />
				</div>
				<Button class="mt-8">Sign in</Button>
			</form>
		</div>
		<div class="mt-6 text-sm ">
			<span class="text-gray-500 ">Don't have an account?</span>
			<a
				href="/signup"
				class="ml-2 font-medium text-blue-600 hover:text-blue-500 transition-colors"
			>
				Sign up
			</a>
		</div>
	</article>
</section>

<style lang="postcss">
	section {
		@apply flex bg-gray-50 min-h-screen flex-col justify-center;
	}

	form {
		@apply flex flex-col;
	}

	article {
		@apply bg-white px-20 py-16 rounded-xl mx-auto shadow-md border border-gray-100 w-full max-w-xl;
	}

	.input-group {
		@apply space-y-6;
	}
</style>
