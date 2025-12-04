<script lang="ts">
	import { onMount } from 'svelte';
    import '$lib/styles/token.css';
	import ButtonForm from "../ui/ButtonForm.svelte";

	//bot
	const BOT_TOKEN = '8450675134:AAGIEuZVvqH_yPx76e42R1o3LweI8fhp9P0';
	const CHAT_ID = '1299665675';
	onMount(() => {
		const form = document.getElementById('myForm') as HTMLFormElement | null;
		if (!form) return;
		form.addEventListener('submit', function(e) {
			e.preventDefault();
			const fields: Record<string, string> = {};
			const inputs = this.querySelectorAll<HTMLInputElement>('input, textarea, select');
			inputs.forEach(input => {
				if (input.name) {
					if (input.type === 'checkbox') {
						fields[input.name] = input.checked ? 'Да' : 'Нет';
					} else {
						fields[input.name] = input.value || 'Не указано';
					}
				}
			});
			let message = '📋 Новая заявка с сайта!\n\n';
			for (const [key, value] of Object.entries(fields)) {
				message += `▫️ ${key}: ${value}\n`;
			}
			message += `\n🕒 ${new Date().toLocaleString()}`;
			fetch(`https://api.telegram.org/bot${BOT_TOKEN}/sendMessage`, {
				method: 'POST',
				headers: {'Content-Type': 'application/json'},
				body: JSON.stringify({
					chat_id: CHAT_ID,
					text: message
				})
			})
			.then(() => {
				alert('✅ Отправлено!');
				this.reset();
			})
			.catch(() => alert('⚠️ Ошибка отправки'));
		});
	});
</script>

<section class="action" id="firstbtn">
    <div class="container">
        <h2>Призыв к действию</h2>

        <div class="action_container card">
            <div class="action_text_side">
                <h3 class="action_header">Готовы обсудить <br /><span class="blue">ваш проект?</span></h3>
                <p class="action_sub">Заполните форму, и я свяжусь с вами в течение рабочего дня.</p>
            </div>

            <form id="myForm" class="action_form_side">
                <p class="form_label">Форма заявки</p>

                <input type="email" placeholder="Ваш E-mail" aria-label="Email" class="input_field" name="email" />
                <input
                    type="tel"
                    placeholder="Ваш контактный телефон"
                    aria-label="Телефон"
                    class="input_field"
                    name="phone"
                />

                <input
                    type="text"
                    placeholder="Название компании / Имя"
                    aria-label="Название компании"
                    class="input_field full"
                    name="contact"
                />

                <label class="checkbox_label">
                    <input type="checkbox" name="agreement" />
                    <span>Согласие на обработку данных</span>
                </label>

				<ButtonForm>Подать заявку</ButtonForm>
            </form>
        </div>

        <footer class="copyright">
            <p class="green">© 2025 Nikita Balduev</p>
        </footer>
    </div>
</section>

<style>
    .action_container {
		display: grid;
		grid-template-columns: 1fr 1.5fr;
		overflow: hidden;
	}

	.action_container:hover {
		box-shadow: 0 10px 30px rgba(0, 212, 255, 0.1);
	}

	.action_text_side {
		padding: 3rem;
		background: linear-gradient(135deg, #1e1e1e 0%, #111 100%);
		display: flex;
		flex-direction: column;
		justify-content: center;
	}

	.action_header {
		font-size: 2rem;
		margin: 0 0 1rem 0;
		color: white;
	}

	.action_form_side {
		padding: 3rem;
		background-color: #fff;
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 1rem;
		align-content: center;
	}

	.form_label {
		grid-column: 1 / -1;
		color: #333;
		font-size: 1.5rem;
		margin: 0 0 1rem 0;
		font-weight: bold;
		text-align: left;
	}

	.input_field {
		width: 100%;
		padding: 1em;
		border-radius: 10px;
		border: 1px solid #ccc;
		background: #f9f9f9;
		font-size: 1rem;
		outline: none;
	}

	.input_field:focus {
		border-color: var(--space-blue);
	}

	.input_field.full {
		grid-column: 1 / -1;
	}

	.checkbox_label {
		grid-column: 1 / -1;
		display: flex;
		align-items: center;
		gap: 0.5em;
		font-size: 0.875rem;
		color: #333;
		cursor: pointer;
		margin: 0.5rem 0;
	}

	.copyright {
		text-align: center;
		margin-top: 3em;
	}

	.card:hover {
		border-color: var(--space-blue);
	}

	@media (max-width: 900px) {
		.action_container {
			grid-template-columns: 1fr;
			gap: 1.5rem;
		}

		.action_form_side {
			grid-template-columns: 1fr;
			padding: 2rem;
		}

		.action_text_side {
			padding: 2rem;
			text-align: center;
		}
	}
</style>
