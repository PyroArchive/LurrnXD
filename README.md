-var garageSpotRowsNeeded=6;var more=(garageSpotRowsNeeded*15)*2;var empty_spots;var mother=document.querySelector(".garage");var none=["none"]
var arr=Array.from(document.querySelectorAll(".garage-spot > .garage-vehicle > .garage-vehichleImage")).map(item=>window.getComputedStyle(item,!1).backgroundImage);var painted=arr.filter(v=>(none.indexOf(v)===-1));painted=painted.map(myFunction)
function myFunction(num){if(num.includes("painted/")){return num.slice(44,-18)}}
painted=painted.filter(function(el){return el!=null});painted=painted.map(Number);console.log("painted "+painted)
arr=arr.filter(v=>(none.indexOf(v)===-1));arr=arr.map(el=>el.slice(36,-14));arr=arr.map(Number);arr=arr.filter(function(value){return!Number.isNaN(value)});arr=arr.concat(painted)
console.log("Original cars: "+arr)
var rmvNames=document.querySelectorAll('.garage-spot > .garage-vehicle > .garage-vehichleImage[data-tip]'),array=[],i;for(i=0;i<rmvNames.length;i+=1){array.push(rmvNames[i].dataset.tip)}
console.log("names removed: "+array);for(var gS=0;gS<more;gS++){var newSpot=document.createElement("div");newSpot.className="garage-spot is-empty";newSpot.innerHTML='<div draggable="true" class="garage-vehicle"><div class="garage-vehichleImage"></div></div>'+'<button class="btn btn--tertiary btn--xs btn--thinner garage-spotBtn">Sell</button>';mother.appendChild(newSpot);empty_spots=document.querySelectorAll(".is-empty > .garage-vehicle > .garage-vehichleImage")}
