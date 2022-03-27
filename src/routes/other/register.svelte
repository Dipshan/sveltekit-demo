<script>
	const handleClick = (e) => {
		e.preventDefault;
	};
</script>

<form type="submit">
	<div class="container">
		<div class="form-card">
			<h1>Register</h1>
			<div class="form-data">
				<label for="name">Enter Your Name </label>
				<input id="name" type="text" />
			</div>
			<div class="form-data">
				<label for="name"> Enter Your Email </label>
				<input id="name" type="text" />
			</div>
			<div class="form-data">
				<label for="name">Enter Your Password </label>
				<input id="name" type="text" />
			</div>
			<div class="form-data">
				<label for="name">Confirm your password </label>
				<input id="name" type="text" />
			</div>
			<button onClick={handleClick}>Register</button>
			<p>
				Already have an account ? <span><a class="re-direct" href="/login">Login here</a></span>
			</p>
		</div>
	</div>
</form>

<style>
	.container {
		display: flex;
		align-items: center;
		justify-content: center;
		height: 100vh;
	}
	.form-card {
		padding: 0 20px 20px;
		border: 0.1px solid black;
		border-radius: 5px;
		width: 500px;
	}
	.form-data {
		display: flex;
		flex-direction: column;
		gap: 10px;
		margin-bottom: 20px;
	}
	input {
		padding: 10px;
		border: 0.1px solid black;
		outline: none;
		border-radius: 5px;
	}
	button {
		padding: 10px;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 1rem;
		border: 0.1px solid black;
		border-radius: 5px;
	}
	.re-direct {
		text-decoration: none;
	}
	.re-direct:hover {
		color: red;
	}
</style>
