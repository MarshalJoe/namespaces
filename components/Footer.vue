<template>
	<footer>
		<div class="footer-links">
			<ul>
				<li><a class="footer-links__link" href="">Github</a></li>
				<li><a class="footer-links__link" href="">Twitter</a></li>
				<li><a class="footer-links__link" href="">Contact</a></li>
			</ul>			
		</div>
	</footer>
</template>

<style>
	footer {
		line-height: 35px;
		display: table;
		border-top: 5px solid grey;
		height: 25px;
		width: 100%;
		background-color: #36454f;
		color:white;

	}

	.footer-links {
		display: table-cell;
		vertical-align: middle;
		text-align: center;
	}

	.footer-links ul {
		list-style: none;
	}

	.footer-links ul li {
		width:75px;
		display:inline;
	}

	.footer-links__link {
		color:white;
	}

	.footer-links__link:hover {
		color:white;
	}
</style>