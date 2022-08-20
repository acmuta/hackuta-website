<script>
    export let from;
    export let to;
    let total = 0, days = 0, hours = 0, minutes = 0, seconds = 0;
    let finished = false;

    function getTimeRemaining(endtime){
        total = Date.parse(from) - Date.parse(new Date().toString());
    }

    const now = Date.parse(new Date().toString())
    if(Date.parse(to) - now > 0)
    {
        finished = true;
    }

    $: seconds = Math.floor( (total/1000) % 60 );
    $: minutes = Math.floor( (total/1000/60) % 60 );
    $: hours = Math.floor( (total/(1000*60*60)) % 24 );
    $: days = Math.floor( total/(1000*60*60*24) );

    const UpdateTimer = setInterval(() => {getTimeRemaining(from)}, 1000);

</script>
<div id="countdown">
    {#if total >= 0}
    <div>
        <span class="big days">{days.toLocaleString('en-US', {minimumIntegerDigits: 2})}</span>
        <div class="small">Days</div>
    </div>
    <span class="colon">:</span>
    <div>
        <span class="big hours">{hours.toLocaleString('en-US', {minimumIntegerDigits: 2})}</span>
        <div class="small">Hours</div>
    </div>
    <span class="colon">:</span>
    <div>
        <span class="big minutes">{minutes.toLocaleString('en-US', {minimumIntegerDigits: 2})}</span>
        <div class="small">Minutes</div>
    </div>
    <span class="colon">:</span>
    <div>
        <span class="big seconds">{seconds.toLocaleString('en-US', {minimumIntegerDigits: 2})}</span>
        <div class="small">Seconds</div>
    </div>
    {:else if !finished}
        <div class="finished">Ended</div>
    {:else}
        <div class="happening">Now active</div>
    {/if}
</div>

<style lang="scss">
#countdown
{
	text-align: center;
	> div
	{
		display: inline-block;
		
		.big
		{
		    font-size: 2rem;
		}
		.small
		{
			font-size: 1rem;
			opacity: 0.65;
		}
	}
	.colon
	{
		font-size: 4rem;
		padding: 0 1rem;
		position: relative;
		top: -0.25rem;
		opacity: 0.85;
	}
	.happening
	{
		color: lime;
        font-size: 2.5rem;
	}
	.finished
	{
		color: white;
        font-size: 2.5rem;
	}
}
</style>