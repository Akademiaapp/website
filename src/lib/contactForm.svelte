<script lang="ts">
	import Input from './components/ui/input/input.svelte';
	import { Textarea } from './components/ui/textarea';
	import Button from './components/ui/button/button.svelte';
</script>

<div class="p-10">
	<form
		action=""
		method="post"
		class="flex h-full flex-col gap-4 lg:max-w-[20rem] xl:max-w-[30rem] 2xl:max-w-[40rem]"
	>
		<h1 class="font-bold text-4xl strikethrough">Kontakt os</h1>
		<p class="strikethrough">
			Har du spørgsmål, ris eller ros? Så tøv ikke med at kontakte os! Vi vil gøre vores bedste for
			at besvare din henvendelse hurtigst muligt.
		</p>
		<div class="flex flex-row gap-4">
			<Input type="text" name="frist_name" placeholder="Fornavn" />
			<Input type="text" name="last_name" placeholder="Efternavn" />
		</div>
		<Input type="email" name="email" placeholder="Email" />
		<Textarea name="message" placeholder="Besked" class="min-h-20 flex-1 resize-none" />
		<Input type="text" name="honeypot" style="display:none" />
		<input type="hidden" name="accessKey" value="" />
		<input type="hidden" name="subject" value="Contact us from - akademia.cc" />
		<input type="hidden" name="replyTo" value="@" />
		<input type="hidden" name="redirectTo" value="https://akademia.cc/" />
		<Button type="submit" disabled class="text-lg w-48 h-12">Send besked</Button>
	</form>
</div>
