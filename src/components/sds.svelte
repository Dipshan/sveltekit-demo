<script>
	let name = 'Example for hiding scrollbar yet keeping function';
	let hideScroll = false;
	let afewblocks = [];
	for (let i = 0; i < 30; i++) { afewblocks.push(i); } // sorry for the crudeness...
</script>

<body class:hideScroll id="scrollingBlock">	
	<h3>{name}</h3>
	<label>
		<input type=checkbox bind:checked={hideScroll}>
		Hide scrollbar
	</label>
	<div>
		scrollbar {hideScroll ? 'hidden' : 'shown'}
	</div>
	<div class="spacer" />
	<div>
		{#each afewblocks as blk}
			<div>	Some text to enable scrolling.. <br>
						Some text to enable scrolling.. <br>
						Some text to enable scrolling.. <br>
 			</div>
		{/each}
	</div>
</body>

<style>
	.hideScroll::-webkit-scrollbar { display: none; }
	.hidescroll {
  	-ms-overflow-style: none;  /* IE and Edge */
  	scrollbar-width: none;     /* Firefox */
	}
	.spacer { height: 10vh; }
	#scrollingBlock {
		border: 2px solid black;
		/*box-shadow: 10px 5px 5px red;*/
		overflow-y: scroll;
	}
</style>