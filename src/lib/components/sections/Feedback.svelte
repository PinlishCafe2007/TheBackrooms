<script>
    import '$lib/styles/token.css';
	import { feedbackImages } from '$lib/data/feedbackImages.js';
</script>

<section class="feedback">
    <div class="container">
        <h2>Отзывы</h2>
        <div class="split_grid">
            <!-- Text on the left -->
            <div class="card feedback_info">
                <div class="quote_icon">“</div>
                <p class="feedback_text">
                    «После запуска лендинга с виртуальной экскурсией количество желающих посетить нашу школу в День открытых дверей выросло втрое. Это лучший способ показать всё самое интересное и привлечь будущих учеников.»
					— Директор Табакирова Ирина Леонтьевна, г.Абакан МБОУ"СОШ№26"             
				</p>
                <div class="quote_author">— Довольный Клиент</div>
            </div>

            <!-- Images grid -->
            <div class="feedback_visuals">
                {#each feedbackImages as src}
                    <div class="feedback_img_card">
                        <img {src} alt="Скриншот отзыва" />
                    </div>
                {/each}
            </div>
        </div>
    </div>
</section>

<style>
    .feedback_info {
		padding: 2.5rem;
		position: relative;
	}

	.feedback_info:hover {
		box-shadow: 0 10px 30px rgba(0, 212, 255, 0.1);
	}

	.quote_icon {
		font-size: 5rem;
		color: var(--space-green);
		line-height: 0.5;
		position: absolute;
		top: 1rem;
		left: 1rem;
		opacity: 0.3;
	}

	.feedback_text {
		position: relative;
		z-index: 1;
		font-style: italic;
	}

	.quote_author {
		margin-top: 1.5rem;
		color: var(--space-blue);
		font-weight: bold;
		text-align: right;
	}

	.feedback_visuals {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
		gap: 1rem;
	}

	.feedback_img_card img {
		width: 100%;
		height: 100%;
		object-fit: cover;
		border-radius: 20px;
		border: 1px solid #333;
	}
	.card:hover {
		border-color: var(--space-blue);
	}
	@media (max-width: 900px) {
		.split_grid {
			grid-template-columns: 1fr;
			gap: 1.5rem;
		}
	}
</style>