
<script lang="ts">
    import Input from "./components/ui/input/input.svelte";
    import { Textarea } from "./components/ui/textarea";
    import Label from "./components/ui/label/label.svelte";
	import Button from "./components/ui/button/button.svelte";
</script>

<form action="https://api.staticforms.xyz/submit" method="post" class="grid gap-2 max-w-96">
    <h1 class="font-bold text-2xl">
        Kontakt os
    </h1>
    <div class="flex flex-row gap-2">
        <Input type="text" name="frist_name" placeholder="Fornavn" />
        <Input type="text" name="last_name" placeholder="Efternavn" />
    </div>
    <Input type="email" name="email" placeholder="Din email" />
    <Textarea name="message" placeholder="Skriv din besked her" />
    <Input type="text" name="honeypot" style="display:none" />
    <input type="hidden" name="accessKey" value="530612c8-1297-4f59-a4cf-d88352ffb570">
    <input type="hidden" name="subject" value="Contact us from - akademia.cc" />
    <input type="hidden" name="replyTo" value="@">
    <input type="hidden" name="redirectTo" value="https://akademia.cc/">
    <Button type="submit" class="text-base">Send</Button>
</form>