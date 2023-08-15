<script>
    let numberOfDots = 60;
  
    function createDots() {
      let arms = [];
      for (let i = 0; i < numberOfDots; i++) {
        arms.push({
          rotation: Math.floor(Math.random() * 541) + 20,
          transition: Math.floor(Math.random() * 6) + 3
        });
      }
      return arms;
    }
  
    let arms = createDots();
  
    function loader() {
      arms = arms.map(arm => ({
        rotation: Math.floor(Math.random() * 541) + 20,
        transition: Math.floor(Math.random() * 6) + 3
      }));
    }
  
    function loop() {
      loader();
      setTimeout(loop, Math.floor(Math.random() * 4001) + 1000);
    }
  
    loop();
  </script>
  
  <p id="loading" class:glowing={true}>LOADING</p>
  <div id="container">
    {#each arms as arm, i}
      <div class="arm" style="transform: rotate({arm.rotation}deg); transition: {arm.transition}s ease-out;">
        <div class="dot"></div>
      </div>
    {/each}
  </div>
  
<style>
@import url('https://fonts.googleapis.com/css?family=Asap:400,500,700');

body {
	margin: 0;
	width: 100%;
	height: 100%;
	position: absolute;
	display: flex;
	display: -webkit-flex;
	display: -moz-flex;
	display: -ms-flex;
	font-family: 'Asap', sans-serif;
}

a {
	text-decoration: none;
	opacity: .6;
	padding: 60px;
	font-weight: 800;
	position: absolute;
	right: 0px;
	bottom: 0px;
	font-size: 1.4em;
}

a:hover {
	opacity: 1;
}

#loading {
	margin: auto;
	width: 400px;
	height: 10px;
	text-align: center;
	position: absolute;
	left: calc(50% - 200px);
	top: calc(50% - 5px);
	letter-spacing: .5em;
	font-size: .7em;
}

.animate {
	animation: animate .4s linear forwards;	
}

@keyframes animate {
	to {
		margin-bottom: 20px;
	}
}

#container {
	width: 300px;
	height: 300px;
	margin: auto;
	position: absolute;
	left: calc(50% - 150px);
	top: calc(50% - 150px);
}

.arm {
	overflow: hidden;
	position: absolute;
	left: calc(50% - 3px);
	bottom: 50%;
	height: 50%;
	width: 6px;
	margin: auto;
	transform-origin: center bottom;
}

.dot {
	width: 6px;
	height: 6px;
	border-radius: 100px;
	opacity: .2;
	background: rgb(245, 39, 39);
}

.glowing {
    animation: glow 2s infinite alternate;
  }

  @keyframes glow {
    0% {
      color: black;
      text-shadow: none;
    }
    100% {
      color: red;
      text-shadow: 0 0 10px red;
    }
  }


</style>

