<script>
    import { benefits } from '$lib/data/benefits.js';
</script>

<section class="edge">
    <div class="container">
        <h2>Преимущества</h2>
        <div class="grid_3_col">
            {#each benefits as item}
                <div class="card edge_card">
                    <h3 class="card_title">{item.title}</h3>
                    <p class="card_desc">{item.desc}</p>
                </div>
            {/each}
        </div>
    </div>
</section>

<style>
    .edge_card {
		padding: 2rem;
		text-align: center;
		display: flex;
		flex-direction: column;
		justify-content: center;
	}

	.edge_card:hover {
		box-shadow: 0 10px 30px rgba(0, 212, 255, 0.1);
	}

	.card_title {
		color: var(--space-green);
		font-size: 1.5rem;
		margin: 0 0 0.5rem 0;
	}

	.card_desc {
		margin: 0;
		opacity: 0.9;
	}
	.card:hover {
		border-color: var(--space-blue);
	}
	@media (max-width: 900px) {
		.grid_3_col {
			grid-template-columns: 1fr;
			gap: 1.5rem;
		}
	}
</style>