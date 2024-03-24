<script lang="ts">
    import Input from "./components/ui/input/input.svelte";
    import { Textarea } from "./components/ui/textarea";
	import Button from "./components/ui/button/button.svelte";
</script>

<div class="p-10">
    <form action="https://api.staticforms.xyz/submit" method="post" class="grid gap-3 max-w-lg">
        <h1 class="font-bold text-4xl">
            Kontakt os
        </h1>
        <p class="">
            Har du spørgsmål, ris eller ros? Så tøv ikke med at kontakte os! Vi vil gøre vores bedste for at besvare din henvendelse hurtigst muligt.
        </p>
        <div class="flex flex-row gap-3">
            <Input type="text" name="frist_name" placeholder="Fornavn" />
            <Input type="text" name="last_name" placeholder="Efternavn" />
        </div>
        <Input type="email" name="email" placeholder="Email" />
        <Textarea name="message" placeholder="Besked" />
        <Input type="text" name="honeypot" style="display:none" />
        <input type="hidden" name="accessKey" value="530612c8-1297-4f59-a4cf-d88352ffb570">
        <input type="hidden" name="subject" value="Contact us from - akademia.cc" />
        <input type="hidden" name="replyTo" value="@">
        <input type="hidden" name="redirectTo" value="https://akademia.cc/">
        <Button type="submit" class="text-base w-48">Send besked</Button>
    </form>
</div>