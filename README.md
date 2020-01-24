# iSaidLetThereBeLightbox
A simple light box with some animation

# The JS that makes it work

`let lightboxLinks = document.querySelectorAll('.lightboxify'); // this uses querSelctorAll() to select all tags in HTML with a class of () and sets them to a string to be called on`





`let letThereBeLightBox = function(event){
	event.preventDefault() // stops the clicking of the link from navigating away from the page (a link's default behavior)`
	

	let backDrop =document.createElement('div') //creates a div in the html and sets it to a string ot be called on 
	
	backDrop.classList.add('lightbox-backdrop') //calls on the classList and adds the specified class to the given element, allowing it to be styled by CSS
	
	backDrop.style.opacity = 0; //sets up the beggining of a fade in animation by setting opacity to 0
	
	setTimeout(function() { //creates a timeout function of a fraction of a second to allow CSS to read what JS declared
	
		backDrop.style.opacity = 1;	//sets up the end of the animation by setting the opacity to 1
		
		backDrop.stylr.transition = '1s' //sets the duration of the animation to 1 second
		
	}, 10) //sets the setTimeout to a milli second
	
	document.body.appendChild(backDrop) // adds the called upon element in () to the desired element, in this case document, making it its child
	
	let whiteLight = document.createElement('div') //creates a div in the html and sets it to a string ot be called on
	
	whiteLight.classList.add('lightbox') //calls on the classList and adds the specified class to the given element, allowing it to be styled by CSS
	
	whiteLight.style.opacity = 0; //sets up the beggining of a fade in animation by setting opacity to 0
	
	setTimeout(function() { //creates a timeout function of a fraction of a second to allow CSS to read what JS declared
	
		whiteLight.style.opacity = 1; //sets up the end of the animation by setting the opacity to 1
		
		whiteLight.style.transition= '2s'; //sets the duration of the animation to 1 second
		
	}, 10) //sets the setTimeout to a milli second
	
	document.body.appendChild(whiteLight)// adds the called upon element in () to the desired element, in this case document, making it its child

	let largeImage = document.createElement('img') //creates a img in the html and sets it to a string ot be called on
	
	largeImage.setAttribute('src', this.href) //this gives the element img an attribute tag of src, and then *this* says that whichever picture is clicked is the href tag we want to apply to the src.
	
	whiteLight.appendChild(largeImage) // adds the called upon element in () to the desired element, in this case whiteLight, making it its child

	let closeBtn = document.createElement('div') //this creats and adds a div from JS in the html, name(string) so we can call on it 
	
	closeBtn.classList.add('lightbox-close') //calls on the classList and adds the specified class to the given element, allowing it to be styled by CSS
	
	whiteLight.appendChild(closeBtn) // adds the called upon element in () to the desired element, in this case whiteLight, making it its child

	let beGoneLightBox = function(){ // creates a function and names said function so we can call it later
	
		whiteLight.remove() //this removes the whiteLight div from the page
		
		backDrop.remove()//this removes the backDrop div from the page
	}

	closeBtn.addEventListener('click', beGoneLightBox)//this adds an eventListener to listen for the 'click' event to happen on the close button, when that happens it calles on the function beGoneLightBox, which removes the backdrop and light box.
	
	backDrop.addEventListener('click', beGoneLightBox)//this adds an eventListener to listen for the 'click' event to happen anywhere on the backdrop, when that happens it calles on the function beGoneLightBox, which removes the backdrop and light box.
	
	window.addEventListener('keyup', function(event) { //adds an event listener of 'keyup' to the entire viewable window, than creates a function to execute when the 'keyup happens'
	
   	 if(event.code === "Escape") { //this if statment says that the function is to only execute if the 'keyup' events keycode is "Escape" making it so only the escape button works for the desired effect 
	 
       beGoneLightBox() //if the escape key is clicked the function beGoneLightBox will run and it will remove the whiteLight and backdrop
    	}
	})
`}`

`for (var i = 0; i < lightboxLinks.length; i++) { //creates a for loop to run through all of lightBoxLinks to apply the letThereBeLightBox function to all of them`

	`lightboxLinks[i].addEventListener('click', letThereBeLightBox) //when clicked`
`}`

															  
