<script>
	export let data;
	// console.log(load.status);
	import { onMount } from 'svelte';

	onMount(() => {
		return () => {};
	});
</script>

<section class="filter-sort-section service-items">
	<div class="filter-block">
		<h3 class="filter-title">Filteren</h3>
		<div class="filter-sub-block">
			<div class="filter-1">
				<h4>SDG</h4>
			</div>
			<div class="filter-2">
				<h4>Thema</h4>
				<span>Vakantie</span><input type="checkbox" id="vehicle1" name="vehicle1" value="Bike" />
				<span>Sport</span><input type="checkbox" id="vehicle1" name="vehicle1" value="Bike" />
				<span>Natuur</span><input type="checkbox" id="vehicle1" name="vehicle1" value="Bike" />
				<a class="btn-filter">Pas filter toe</a>
				<button type="button" class="btn-more">Meer</button>

				<h3>Filter</h3>
				<div class="read-more-cont">
					<span>
						Netwerkorganisatie<input
							type="checkbox"
							id="vehicle1"
							name="vehicle1"
							value="Bike"
						/></span
					>
					<span
						>Vereniging / club<input
							type="checkbox"
							id="vehicle1"
							name="vehicle1"
							value="Bike"
						/></span
					>
					<span
						>Onderneming<input type="checkbox" id="vehicle1" name="vehicle1" value="Bike" /></span
					>
					<span>
						Woningcorporatie<input
							type="checkbox"
							id="vehicle1"
							name="vehicle1"
							value="Bike"
						/></span
					>
					<span>
						Zorginstelling<input type="checkbox" id="vehicle1" name="vehicle1" value="Bike" /></span
					>
					<span
						>Onderwijsinstellling<input
							type="checkbox"
							id="vehicle1"
							name="vehicle1"
							value="Bike"
						/></span
					>
					<span> Overheid<input type="checkbox" id="vehicle1" name="vehicle1" value="Bike" /></span>
					<span
						>Informele groep<input
							type="checkbox"
							id="vehicle1"
							name="vehicle1"
							value="Bike"
						/></span
					>
					<span>
						Non-profit<input type="checkbox" id="vehicle1" name="vehicle1" value="Bike" /></span
					>
				</div>
			</div>
		</div>
	</div>

	<div class="sort-block">
		<form>
			<label for="sort" class="go_result-sort-label">Sorteer op:</label>

			<select id="sort" name="sort" class="form-control float-right">
				<option value="75135" selected="">Meest gedeeld</option>
				<option value="system:creation_date">Meest recent geplaatst</option>
			</select>
		</form>
	</div>
</section>

<div class="popup-box">
	<div class="popup-content">
		<div class="popup-header">
			<h3></h3>
			<span class="popup-close-icon">&times;</span>
		</div>
		<div class="popup-body"></div>
		<div class="popup-footer">
			<button class="btn popup-close-btn">Pas filter toe</button>
		</div>
	</div>
</div>

<h1 class="title-wensen">Alle Wensen<span class="filsort-result">4</span></h1>

<style>
	.title-wensen {
		margin-bottom: 15px;
		margin-top: 20px;
	}
	.filsort-result {
		color: #0594c6;
		margin-left: 10px;
	}

	/* Filter en sorteer  */
	.filter-sort-section {
		display: flex;
		margin-bottom: 1rem;
		margin-top: 3rem;
	}

	@media only screen and (max-width: 780px) {
		.filter-sort-section {
			display: block;
		}
		.sort-block {
			margin-left: 0px;
			margin-top: 60px;
		}
	}

	@media only screen and (min-width: 780px) {
		.sort-block {
			margin-left: 30px;
		}
	}

	/* Sorteren */
	.sort-block {
		position: relative;
	}

	.sort-block form {
		position: absolute;
		bottom: 0px;
	}

	.sort-block form label {
		font-weight: 600;
	}

	#sort {
		border-radius: 0;
		border: 1px solid #333;
		padding: 0.2rem 0.33rem;
		height: 30px;
		margin-right: 0.5rem;
		margin-top: 5px;
		color: #495057;
	}

	/* Filteren */
	.filter-block {
		position: relative;
		background-color: #f7f7f7;
		border-radius: 0.5rem;
	}

	.filter-2 h3 {
		display: none;
	}

	.filter-title {
		position: absolute;
		top: -30px;
		left: 10px;
		padding: 0.7rem;
		min-width: 150px;
		background-color: #009ee2;
		color: white;
		border-radius: 0.5rem;
	}

	.filter-sub-block {
		padding: 1rem;
		padding-top: 31px;
		height: 175px;
	}

	.filter-sub-block h4 {
		margin-bottom: 5px;
	}

	.filter-sub-block span {
		margin-bottom: 10px;
	}

	.filter-sub-block input[type='checkbox'] {
		margin-left: 10px;
		margin-right: 10px;
		cursor: pointer;
	}

	.filter-sub-block .btn-more {
		position: absolute;
		bottom: 0;
		right: 0;
		margin: 15px 20px 15px 15px;
		text-decoration: underline;
		text-underline-offset: 2px;
		color: blue;
		border: none;
		background-color: #f7f7f7;
		cursor: pointer;
	}

	.filter-sub-block .btn-filter {
		position: absolute;
		bottom: 0;
		left: 0;
		margin: 15px 20px 10px 10px;
		padding: 10px;
		border-radius: 0.5rem;
		background-color: #f0eded;
		cursor: pointer;
		border: none;
		font-size: 14px;
	}

	body {
		font-family: sans-serif;
		margin: 0;
		line-height: 1.5;
	}

	* {
		box-sizing: border-box;
		margin: 0;
	}

	.read-more-cont {
		display: none;
	}

	.popup-box {
		position: fixed;
		height: 100%;
		width: 100%;
		left: 0;
		top: 0;
		background-color: rgba(0, 0, 0, 0.5);
		z-index: 500;
		visibility: hidden;
		opacity: 0;
		transition: all 0.5s ease-in-out;
	}
	.popup-box.open {
		visibility: visible;
		opacity: 1;
	}
	.popup-box .popup-content {
		background-color: #ffffff;
		width: 600px;
		position: absolute;
		left: 50%;
		top: 50%;
		transform: translate(-50%, -50%);
		border-radius: 8px;
	}

	.popup-box .popup-header {
		padding: 15px 40px 15px 15px;
		border-bottom: 1px solid #dddddd;
	}
	.popup-box .popup-header h3 {
		margin: 0;
		color: #009ee2;
		font-size: 20px;
	}
	.popup-box .popup-header .popup-close-icon {
		position: absolute;
		height: 30px;
		width: 30px;
		text-align: center;
		color: #555555;
		font-size: 28px;
		line-height: 30px;
		right: 5px;
		top: 5px;
		cursor: pointer;
	}
	.popup-box .popup-body {
		position: reletive;
		padding: 15px;
		max-height: 300px;
		overflow-y: auto;
		display: flex;
		flex-direction: column;
	}

	.popup-box .popup-body input[type='checkbox'] {
		position: absolute;
		left: 200px;
		margin-top: 5px;
	}

	.popup-box .popup-body span {
		margin-bottom: 5px;
	}

	.popup-box .popup-body img {
		width: 100%;
		display: block;
		margin-top: 15px;
	}
	.popup-box .popup-body p {
		font-size: 16px;
		color: #555555;
		margin: 0 0 15px;
	}
	.popup-box .popup-footer {
		padding: 15px;
		border-top: 1px solid #dddddd;
		text-align: right;
	}
	.popup-box .popup-footer .btn {
		padding: 8px 15px;
		color: #fff;
		font-size: 16px;
		border: none;
		background-color: #009ee2;
		cursor: pointer;
		border-radius: 4px;
	}
	.popup-box .popup-footer .btn:focus {
		outline: none;
	}

	/*responsive*/

	@media (max-width: 767px) {
		.services .service-items .item {
			flex: 0 0 100%;
			max-width: 100%;
		}
		.popup-box .popup-content {
			width: calc(100% - 30px);
		}
	}
</style>
