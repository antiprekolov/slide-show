<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>slide-show</title>
</head>
<style>
	.header{
		display: flex;
		justify-content: center;
	}

	.slide-show{
		width: auto;
	}

	.slide{
		height: 25rem;
		width: 60rem;
		background-size: cover;
		display: flex;
		justify-content: space-between;
	}

	.left, .right{
		align-self: center;
		color: brown;
		font-size: 2rem;
		font-weight: 10px;
		background-color: rgba(185, 230, 240, .6);
		padding: 2%;
		border-radius: 10px;
		cursor: pointer;
	}

	.slide-text{
		align-items: flex-end;
	}

	.slide-switch{
		text-align: center;
		margin-top: 10px;
	}

	.dot{
		cursor: pointer;
		height: 13px;
		width: 13px;
		border-radius: 50%;
		background-color: aqua;
		border: 1px solid black;
		display: inline-block;
		margin: 0 12px;
	}
</style>
<body>
	<section class="header">
		<main class="slide-show">
			<div class="slide" style="background-image: url(/puctures/wallpaperbetter.com_1920x1080.jpg)"> 
				<a class="left" onclick="switchSlides(-1)">&#10094;</a>
				<div class="slide-text">1</div>
				<a class="right" onclick="switchSlides(1)">&#10095;</a>
			</div>
			
			<div class="slide" style="background-image: url(/puctures/call-of-duty-modern-warfare-remastered_3840x2160_hcjfh.jpg)"> 
				<a class="left" onclick="switchSlides(-1)">&#10094;</a>
				<div class="slide-text">2</div>
				<a class="right" onclick="switchSlides(1)">&#10095;</a>
			</div>
			
			<div class="slide" style="background-image: url(/puctures/1920x1080_call-of-duty-modern-warfare-remastered.jpg)"> 
				<a class="left" onclick="switchSlides(-1)">&#10094;</a>
				<div class="slide-text">3</div>
				<a class="right" onclick="switchSlides(1)">&#10095;</a>
			</div>
			
			<div class="slide" style="background-image: url(/puctures/165669-kalibr_igry-kiberpank_2077-kalibr-pole_bitvy_2042-ekshn_igra-1920x1080.jpg)"> 
				<a class="left" onclick="switchSlides(-1)">&#10094;</a>
				<div class="slide-text">4</div>
				<a class="right" onclick="switchSlides(1)">&#10095;</a>
			</div>
			
			<div class="slide" style="background-image: url(/puctures/wallpaperbetter.jpg)"> 
				<a class="left" onclick="switchSlides(-1)">&#10094;</a>
				<div class="slide-text">5</div>
				<a class="right" onclick="switchSlides(1)">&#10095;</a>
			</div>
			
			<div class="slide-switch">
				<span class="dot" onclick="showSlides(0)"></span>
				<span class="dot" onclick="showSlides(1)"></span>
				<span class="dot" onclick="showSlides(2)"></span>
				<span class="dot" onclick="showSlides(3)"></span>
				<span class="dot" onclick="showSlides(4)"></span>
			</div>
				
		</main>
	</section>
</body>
<script>
	let counter = 0;
	showSlides(0);
	function switchSlides(diff){
		counter += diff;
		showSlides(counter);
	}

	function showSlides(n){
		counter = n;
		const slides = document.getElementsByClassName('slide');
		if(counter < 0){
			counter = slides.length - 1;
		}else if(counter === slides.length){
			counter = 0;
		}
		for (let index = 0; index < slides.length; index++) {
			slides[index].style.display = 'none';
		}
		slides[counter].style.display = 'flex';
	}

	const slidesRaw = [
		{
			'img': 'img/slide/1.jpg',
			'txt': 'first'
		},
		{
			'img': 'img/slide/2.jpg',
			'txt': 'Second'
		}
	]

	class SlideShow{
		constructor(array){
			this.slides= []
			array.forEach(e => {
				let slide = new Slide(e['img'], e['txt'])
				this.slides.push(slide)
			});
		}
	}

	class Slide{
		constructor(){
			this.element = document.createElement('div');
		}
	}
	
</script>
</html>
