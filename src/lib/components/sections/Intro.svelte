<script>
	import '$lib/styles/token.css';
	import me from '$lib/assets/me-vmake.mp4';
	import ButtonPrimary from '../ui/ButtonPrimary.svelte';
	import ButtonSecondary from '../ui/ButtonSecondary.svelte';
</script>

<section class="hello">
    <div class="container hello_content">
        <div class="hello_text">
            <h1>
                Создаю современные сайты на Svelte, которые
                <span class="blue">приносят прибыль</span>
            </h1> 
            <div class="sub_text_block">
                <p class="description">
                    <span class="green bold">Fullstack Designer:</span>
                    создаю дизайн и сразу превращаю его в работающий сайт на Svelte. Экономлю ваше время и бюджет.
                </p>
                <div class="btns">
                    <a href="#firstbtn"><ButtonPrimary>Обсудить проект</ButtonPrimary></a>
                    <a href="#secondbtn"><ButtonSecondary>Посмотреть кейсы</ButtonSecondary></a>
                </div>
            </div>
        </div>
        <div class="hello_image">
            <video class="me" src={me} preload='metadata' muted loop autoplay>
                <track kind="captions" />
            </video>
        </div>
    </div>
</section>

<style>
    .hello {
		padding-top: 3em;
	}

	.hello_content {
		display: flex;
		align-items: center;
		justify-content: space-between;
		gap: 2em;
		flex-wrap: wrap;
	}

	.hello_text {
		flex: 1 1 500px;
	}

	.hello_image {
		flex: 0 1 300px;
		display: flex;
		justify-content: center;
	}

	.me {
		width: 100%;
		max-width: 300px;
		height: auto;
		aspect-ratio: 1/1;
		border-radius: 50%;
		object-fit: cover;
		border: 4px solid var(--space-green);
	}

	.btns {
		margin-top: 2em;
		display: flex;
		gap: 10px;
		flex-wrap: wrap;
	}
	@media (max-width: 900px) {
		.hello_content {
			flex-direction: column-reverse;
			text-align: center;
		}

		.btns {
			justify-content: center;
		}
	}
</style>
