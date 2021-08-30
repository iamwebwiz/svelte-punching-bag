<script>
    export let healthStatus;
    export let healthState;
    let healthColor = 'green';

    $: if (healthState === 'healthy') {
        healthColor = 'green';
    } else if (healthState === 'weak') {
        healthColor = 'yellow';
    } else {
        healthColor = 'red';
    }
</script>

<div class="relative pt-1 my-5">
    <div class="overflow-hidden h-5 mb-4 text-xs flex rounded bg-gray-200">
        <div style={`width:${healthStatus}%`} class={`shadow-none flex flex-col text-center whitespace-nowrap text-white justify-center bg-${healthColor}-500`}>
            {healthStatus}%
        </div>
    </div>
</div>
