<button class="btn primary form_btn"><slot></slot></button>

<style>
    .btn {
		border: none;
		border-radius: 50px;
		font-size: 1rem;
		padding: 0.8em 2em;
		cursor: pointer;
		transition:
			transform 0.2s,
			opacity 0.2s;
		font-weight: 600;
	}

	.btn.primary {
		background-color: var(--space-green);
		color: #000;
	}

	.btn:hover {
		opacity: 0.9;
		transform: translateY(-2px);
	}

	.btn:active {
		opacity: 0.9;
		transform: translateY(+2px);
	}
    .form_btn {
		grid-column: 1 / -1;
		width: 100%;
		margin-top: 1rem;
	}
</style>