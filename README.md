# Riender olumpics


const reindeers =[

{

name :'Blitzen',

vitesse : 19,

flyDuration : 9,

restDuration :158

},

{

name :'Donner',

vitesse : 19,

flyDuration : 9,

restDuration :164

},

{

name :'Rudolph',

vitesse : 3,

flyDuration : 15,

restDuration :28

},

{

name :'Vixen',

vitesse : 19,

flyDuration : 7,

restDuration :124

},

{

name :'comet',

vitesse : 14,

flyDuration : 10,

restDuration :127

},

{

name :'dancer',

vitesse : 16,

flyDuration : 11,

restDuration :162

},

{

name :'prancer',

vitesse : 25,

flyDuration : 6,

restDuration :143

},

{

name :'Dasher',

vitesse : 14,

flyDuration : 3,

restDuration :38

},

{

name :'Cupid',

vitesse : 25,

flyDuration : 6,

restDuration :145

}

]

const calculateDistance = (reeinder ,travelingTime )=>{

const traveledSegment = Math.floor(travelingTime/(reeinder.flyDuration + reeinder.restDuration));

const segmentRest = travelingTime% (reeinder.flyDuration + reeinder.restDuration);

return ((traveledSegment*reeinder.flyDuration + Math.min(reeinder.flyDuration ,segmentRest ))*reeinder.vitesse)

}

const maxDistanceTraveled = (travelingTime , ...reindeers)=>{

let maxDistance = 0;

const winningTraveledDistance = reindeers.reduce((acc,item)=>{

if(calculateDistance(item,travelingTime) > maxDistance){

maxDistance = calculateDistance(item,travelingTime)

acc = item

}

return maxDistance

},{})

return winningTraveledDistance

}

const winningsReindeersDistace = maxDistanceTraveled(2503 , ...reindeers)

console.log(winningsReindeersDistace)
