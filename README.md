<html>
    <head>
        <title>Using a JS Library: Slideshow library</title>
    </head>
    <body>
        
    <div id="slideshow">
        <img src="https://www.kasandbox.org/programming-images/animals/birds_rainbow-lorakeets.png" alt="Rainbow lorakeets" />
        <img src="https://www.kasandbox.org/programming-images/animals/butterfly.png"alt="Butterfly" />
        <img src="https://www.kasandbox.org/programming-images/animals/cat.png" alt="Cat" />
        <img src="https://www.kasandbox.org/programming-images/animals/crocodiles.png" alt="Crocodiles" />
        <img src="https://www.kasandbox.org/programming-images/animals/fox.png" alt="Fox" />
        
    </div>

    <script>
var slideShow = function(container) {
    this.images = [];
    this.curImage = 0;
    for (i = 0; i < container.childElementCount; i++) {
        this.images.push(container.children[i]);
        this.images[i].style.display = "none";
    }
    
    // Handle going to to the next slide
    var nextSlide = function() {
        for (var i = 0; i < this.images.length; i++) {
            this.images[i].style.display = "none";
        }
        this.images[this.curImage].style.display = "block";
        this.curImage++;
        if (this.curImage >= this.images.length) {
            this.curImage = 0;
        }
        window.setTimeout(nextSlide.bind(this), 1000);
    };
    
    nextSlide.call(this);
};
slideShow(document.getElementById("slideshow"));
