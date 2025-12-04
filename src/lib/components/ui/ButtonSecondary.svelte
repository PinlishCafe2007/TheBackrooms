<button class="btn secondary"><slot></slot></button>

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

	.btn.secondary {
		background-color: transparent;
		border: 2px solid var(--text-color);
		color: var(--text-color);
		margin-left: 10px;
	}

	.btn:hover {
		opacity: 0.9;
		transform: translateY(-2px);
	}

	.btn:active {
		opacity: 0.9;
		transform: translateY(+2px);
	}
</style>
