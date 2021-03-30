---
layout: page
title: About
permalink: /about/
---
<style>
.wrapper-title {
	text-align:center;
	font-size:18pt;
	font-weight:bold;
}
.wrapper-label--bold {
	text-align:center;
	font-size:15pt;
	font-weight:bold;
	color:#778899
}
.flex {
	align-items: center;
	display: flex;
	flex-direction: column;
	justify-content: center;
}
.flex.row {
	flex-direction: row;
}
.flex.wrap {
	flex-wrap: wrap;
}

.hex-wrap {
	display: inline-block;
	height: 80px;
	position: relative;
	text-align: center;
	width: 80px;
}

.hexagon {
	background-color: #04c2c9;
	display: inline-block;
	height: 100%;
	width: calc(100% * 0.57735);
}

.hexagon:before {
	background-color: inherit;
	content: "";
	height: inherit;
	position: absolute;
	right: calc((100% / 2) - ((100% * 0.57735) / 2));
	top: 0;
	transform: rotateZ(60deg);
	width: inherit;
}

.hexagon:after {
	background-color: inherit;
	content: "";
	height: inherit;
	position: absolute;
	right: calc((100% / 2) - ((100% * 0.57735) / 2));
	top: 0;
	transform: rotateZ(-60deg);
	width: inherit;
}
.animated.flip-in-x {
	animation: flipInX 0.75s ease both;
}
@keyframes flipInX {
	from {
		-webkit-animation-timing-function: ease-in;
		animation-timing-function: ease-in;
opacity: 0;
		 -webkit-transform: perspective(400px) rotateY(90deg);
transform: perspective(400px) rotateY(90deg);
	}
	40% {
		-webkit-animation-timing-function: ease-in;
		animation-timing-function: ease-in;
		-webkit-transform: perspective(400px) rotateY(-20deg);
transform: perspective(400px) rotateY(-20deg);
	}
	60% {
opacity: 1;
		 -webkit-transform: perspective(400px) rotateY(10deg);
transform: perspective(400px) rotateY(10deg);
	}
	80% {
		-webkit-transform: perspective(400px) rotateY(-5deg);
transform: perspective(400px) rotateY(5deg);
	}
	to {
opacity: 1;
		 -webkit-transform: perspective(400px);
transform: perspective(400px);
	}
}
.wrapper-bullet {
	max-width: 230px;
	margin: 20px;
}
</style>
  <div class="post-content">
    <p class="wrapper-title">I'm a Front-end devolper</p>
	<div class="flex row label-wrap">
	<div class="flex row-gt-sm">
	<div class="flex wrapper-bullet">
	<div class="hex-wrap waypoint animated flip-in-x" data-animation="flip-in-x">
	<div class="hexagon">
	<i class="mdi mdi-speedometer"></i>
	</div>
	</div>
	<div class="waypoint animated fade-in" data-animation="fade-in">
	<div class="wrapper-label--bold">Fast</div>
	<div class="wrapper-sublabel">
	Fast load times and interaction, my highest
	priority.
	</div>
	</div>
	</div>

	<div class="flex wrapper-bullet">
	<div class="hex-wrap waypoint animated flip-in-x" data-animation="flip-in-x" data-delay=".2s" style="animation-delay: 0.2s;">
	<div class="hexagon">
	<i class="mdi mdi-cellphone-link"></i>
	</div>
	</div>
	<div class="waypoint animated fade-in" data-animation="fade-in" data-delay=".2s" style="animation-delay: 0.2s;">
	<div class="wrapper-label--bold">Responsive</div>
	<div class="wrapper-sublabel">My layouts will work on any device, big or small.</div>
	</div>
	</div>
	</div>
	<div class="flex row-gt-sm">
	<div class="flex wrapper-bullet">
	<div class="hex-wrap waypoint animated flip-in-x" data-animation="flip-in-x" data-delay=".4s" style="animation-delay: 0.4s;">
	<div class="hexagon">
	<i class="mdi mdi-lightbulb-outline"></i>
	</div>
	</div>
	<div class="waypoint animated fade-in" data-animation="fade-in" data-delay=".4s" style="animation-delay: 0.4s;">
	<div class="wrapper-label--bold">Intuitive</div>
	<div class="wrapper-sublabel">Strong preference for easy to use, intuitive UX/UI.</div>
	</div>
	</div>

	<div class="flex wrapper-bullet">
	<div class="hex-wrap waypoint animated flip-in-x" data-animation="flip-in-x" data-delay=".6s" style="animation-delay: 0.6s;">
	<div class="hexagon">
	<i class="mdi mdi-rocket"></i>
	</div>
	</div>
	<div class="waypoint animated fade-in" data-animation="fade-in" data-delay=".6s" style="animation-delay: 0.6s;">
	<div class="wrapper-label--bold">Dynamic</div>
	<div class="wrapper-sublabel">
	Websites don't have to be static, I love making pages interactive.
	</div>
	</div>
	</div>
	</div>
	</div>


  </div>
