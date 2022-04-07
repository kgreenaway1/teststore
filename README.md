# teststore

I went ahead and added a quick mouseover/mouseout eventlistener to the card.html file that will change the src, data-srcset and srcset strings to show the 2nd picture on hover, and back to the first on un-hover.

document.querySelectorAll('.card-image').forEach(function(element) {
element.addEventListener("mouseover", function(){
let newSrc = this.getAttribute('data-tester')
this.src = newSrc;
this.setAttribute("data-srcset", newSrc)
this.setAttribute("srcset", newSrc)
});
element.addEventListener("mouseout", function(){
let ogSrc = this.getAttribute('data-holder')
this.src = ogSrc;
this.setAttribute("data-srcset", ogSrc)
this.setAttribute("srcset", ogSrc)
});
});




in responsive-img.html i added these two tags to make it work (not ideal because hardcoded but it works for test):
data-holder="{{getImageSrcset image 1x=(default fallback_size '160w')}}"  data-tester="https://cdn11.bigcommerce.com/s-qlixn35sfl/products/112/images/377/tp2__31255.1649077654.386.513.jpg"


for the button I added this in the store theme editor.  Then on category.html added another event listener for a click.

let myBtn = document.getElementById('sd-simple-button-editable-1f15f3dc-dd61-481b-b23d-daf1cf44fb86');
    myBtn.addEventListener("click", function(){
        alert('Items added to cart!')
    })
