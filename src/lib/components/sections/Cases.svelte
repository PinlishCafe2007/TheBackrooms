<script>
    import '$lib/styles/token.css';
	import { cases } from '$lib/data/cases.js';
</script>

<section class="keys" id="secondbtn">
	<div class="container">
		<h2>Кейсы</h2>
		<div class="grid_3_col">
			{#each cases as item}
				<div class="card key_card">
					<div class="key_img_wrapper">
						<img src={item.img} alt={item.title} />
					</div>
					<div class="key_content">
						<h3 class="card_title">{item.title}</h3>
						<div class="key_details">
							<p><span class="blue bold">Задача:</span> {item.problem}</p>
							<p><span class="green bold">Решение:</span> {item.solution}</p>
							<p><span class="text-white bold">Итог:</span> {item.result}</p>
						</div>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>

<style>
    .text-white {
		color: white;
	}

    .key_card {
		display: flex;
		flex-direction: column;
	}

	.key_img_wrapper {
		width: 100%;
		height: 200px;
		overflow: hidden;
		border-bottom: 1px solid #333;
	}

	.key_img_wrapper img {
		width: 100%;
		height: 100%;
		object-fit: cover;
		transition: transform 0.3s;
	}

	.key_card:hover .key_img_wrapper img {
		transform: scale(1.05);
	}

	.key_card:hover {
		box-shadow: 0 10px 30px rgba(0, 212, 255, 0.1);
	}

	.key_content {
		padding: 1.5rem;
		display: flex;
		flex-direction: column;
		flex-grow: 1;
	}

	.key_details p {
		margin: 0.5em 0;
		font-size: 0.95rem;
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