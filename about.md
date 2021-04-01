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
	background-color: #F0F8FF;
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
	<div style="width: 100%; text-align: center">
	<img alt="Profile img" style="width: 500px; height: auto" src="https://user-images.githubusercontent.com/22024761/113163863-87170e80-927b-11eb-9522-24c5a4fbd898.png">
	</div>
	<div style="width: 100%; text-align: center">
	<p style="font-size: 15pt; font-weight: bold">Youngje Woo</p>
	</div>
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
	Fast load times, no options
	</div>
	</div>
	</div>

	<div class="flex wrapper-bullet">
	<div class="hex-wrap waypoint animated flip-in-x" data-animation="flip-in-x" data-delay=".2s" style="animation-delay: 0.2s; position: relative; z-index: 1">
	<div class="hexagon">
	</div>
	</div>
	<div style="position: absolute; width: 70px; height: 70px;z-index: 2;">
	<img src="https://user-images.githubusercontent.com/22024761/113174066-fb09e480-9284-11eb-885a-bb25eba04a19.png">
	</div>
	<div class="waypoint animated fade-in" data-animation="fade-in" data-delay=".2s" style="animation-delay: 0.2s;">
	<div class="wrapper-label--bold">Responsive</div>
	<div class="wrapper-sublabel">Must be work on any device</div>
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
	<div class="wrapper-sublabel">From children to the elderly</div>
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
	Don't be have to static
	</div>
	</div>
	</div>
	</div>
	</div>


  </div>
