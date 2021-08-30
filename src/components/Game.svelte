<script>
    import PunchingBag from "./PunchingBag.svelte";
    import BagHealth from "./BagHealth.svelte";
    import GameControls from "./GameControls.svelte";

    let gameEnded = false;
    let healthStatus = 100;
    let healthState = 'healthy';

    $: updateGameStateBasedOnHealthStatus(healthStatus);

    function handleBagPunch() {
        healthStatus = healthStatus - 10;

        if (healthStatus < 0) {
            alert('You already destroyed this punching bag!');
            healthStatus = 0;
        }

        healthStatus = healthStatus;
    }

    function handleGameReset() {
        if (healthStatus === 100) return;
        healthStatus = 100;
        gameEnded = false;
        healthState = 'healthy';
        alert('Game has been reset successfully!');
    }

    function updateGameStateBasedOnHealthStatus(healthStatus) {
        if (healthStatus >= 30 && healthStatus <= 50) healthState = 'weak';
        if (healthStatus < 30) healthState = 'destroyed';
        if (healthStatus === 0) gameEnded = true;
    }
</script>

<main>
    <PunchingBag gameEnded={gameEnded} />
    <BagHealth healthState={healthState} healthStatus={healthStatus} />
    <GameControls gameEnded={gameEnded} punchBag={handleBagPunch} resetGame={handleGameReset} />
</main>
