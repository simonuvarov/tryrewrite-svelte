<script>
	import Button from '../components/Button.svelte';
	import Input from '../components/Input.svelte';
	import { signup } from '../services/auth.service';

	let email = '';
	let password = '';

	const handleSubmit = () => {
		signup({ email, password })
			.then((r) => {
				console.log(r);
				alert(r.accessToken);
			})
			.catch((e) => alert(e));
	};
</script>

<svelte:head>
	<title>Create your Rewrite account</title>
</svelte:head>

<section>
	<article>
		<h2 class="text-left text-2xl font-semibold text-gray-700">Create your Rewrite account</h2>
		<div class="w-full flex flex-col mx-auto max-w-md mt-8">
			<form action="#" method="POST" on:submit|preventDefault={handleSubmit}>
				<div class="input-group">
					<Input bind:value={email} label="Email" type="email" />
					<Input bind:value={password} class="mt-4" label="Password" type="password" />
				</div>
				<Button class="mt-8">Sign up</Button>
			</form>
		</div>
		<div class="mt-6 text-sm">
			<span class="text-gray-500 ">Have an account?</span>
			<a
				href="/signin"
				class="ml-2 font-medium text-blue-600 hover:text-blue-500 transition-colors"
			>
				Sign in
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
