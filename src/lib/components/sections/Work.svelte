<script>
    import '$lib/styles/token.css';
    import { processSteps } from '$lib/data/processSteps.js';
</script>

<section class="work">
    <div class="container">
        <h2>Процесс работы</h2>
        <div class="work_steps">
            <p class="green step_text">
                {processSteps.join(' → ')}
            </p>
        </div>
    </div>
</section>

<style>
    .step_text {
		font-size: 1.3em;
		text-align: center;
	}
</style>