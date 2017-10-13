## Bromium showcase app

An app used to show and compare Bromium and Selenium, as well as give people a quickstart.


## Dynamic creation of an element demo

<button onclick="demoCreate()" id='create-dynamic'>Create element in 2 seconds</button>
<button onclick="destroyDynamic()" id="destroy-dynamic">Destroy element</button>

<script>
	function demoCreate() {
		setTimeout(
			function() { 
				var elemDiv = document.createElement('button');
				elemDiv.addEventListener('click', function() { this.innerHTML = 'I was clicked'});
				elemDiv.innerHTML = 'I was created 2 seconds after the button was clicked';
				elemDiv.id = 'late-creation';
				this.parent.appendChild(elemDiv);
			}, 2000);
	}
	function destroyDynamic() {
		var elem = document.getElementById('late-creation');
		elem.parentNode.removeChild(elem);
	}
</script>
