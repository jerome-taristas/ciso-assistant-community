<script lang="ts">
	import { page } from '$app/stores';
	import ModelForm from '$lib/components/Forms/ModelForm.svelte';
	import { UserEditSchema } from '$lib/utils/schemas';
	import type { PageData } from './$types';

	import { m } from '$paraglide/messages';

	export let data: PageData;
</script>

<div class="card bg-white shadow p-4">
	<ModelForm form={data.form} schema={UserEditSchema} model={data.model} />
</div>
<div class="card bg-white shadow p-4 mt-2">
	<p class="text-gray-500 text-sm">
		{m.setTemporaryPassword1()}
		<a
			href="{$page.url.pathname}/set-password"
			class="text-primary-700 hover:text-primary-500"
			data-testid="set-password-btn">{m.setTemporaryPassword()}</a
		>. {m.setTemporaryPassword2()}.
	</p>
</div>
