# Plop
<!DOCTYPE html>
<html>
<title>
Nik's Slots
</title>
<p id="showBalance"></p>
<p id="showBet"></p>

	
<script>
var balance = 100
var betAmount = 1
document.getElementById("showBalance").innerHTML = "Money = $" + balance;
document.getElementById("showBet").innerHTML = "Current bet = $" + betAmount;


var oneX;
var twoX;
var threeX;
var outcomeOne;
var outcomeTwo;
var outcomeThree;
var winAmount
var apple ="http://images.clipartpanda.com/apple-20clip-20art-apple-clipart.gif";
var cherry ="https://bestclipartblog.com/storage/upload/cherry-clip-art/cherry-clip-art-1.png";
var luckySeven ="http://weclipart.com/gimg/0FC438E92B800FE5/lucky-seven.png";

var slotOne = new Image(100, 100);
slotOne.src = "http://3.bp.blogspot.com/-flOdBWdrnsU/Ugb5HNBulqI/AAAAAAAAHRk/XnY6Y_WKoPo/s1600/question+mark.png";
var slotTwo = new Image(100, 100);
slotTwo.src = "http://3.bp.blogspot.com/-flOdBWdrnsU/Ugb5HNBulqI/AAAAAAAAHRk/XnY6Y_WKoPo/s1600/question+mark.png";
var slotThree = new Image(100, 100);
slotThree.src = "http://3.bp.blogspot.com/-flOdBWdrnsU/Ugb5HNBulqI/AAAAAAAAHRk/XnY6Y_WKoPo/s1600/question+mark.png";
var spunSlotOne = new Image(100, 100);
var spunSlotTwo = new Image(100, 100);
var spunSlotThree = new Image(100, 100);

</script>


Change bet: <button onclick="increaseFunction()">+</button>
<button onclick="decreaseFunction()">-</button>
<p><button onclick="spinFunction()">Spin!</button>
<br>
<button onclick="resetFunction()">Bet Again</button>


<script>
document.body.appendChild(slotOne);
document.body.appendChild(slotTwo);
document.body.appendChild(slotThree);


function increaseFunction() {
betAmount ++;
if (betAmount > 0) {
document.getElementById("showBet").innerHTML = "Current bet = $" + betAmount;
} else {
document.getElementById("showBet").innerHTML = "Betting error";
}}

function decreaseFunction() {
betAmount --;
if (betAmount > 0) {
document.getElementById("showBet").innerHTML = "Current bet = $" + betAmount;
} else {
document.getElementById("showBet").innerHTML = "Betting error";
}}





function spinFunction() {

document.getElementById("winCombinations").innerHTML = null;

balance -= betAmount;
document.getElementById("showBalance").innerHTML = "Money = $" + balance;

oneX = Math.ceil(Math.random() * 6);
twoX = Math.ceil(Math.random() * 6);
threeX = Math.ceil(Math.random() * 6);

if (oneX < 4) {
outcomeOne = apple;
} else if (oneX < 6) {
outcomeOne = cherry;
} else if (oneX == 6) {
outcomeOne = luckySeven;
}

if (twoX < 4) {
outcomeTwo = apple;
} else if (twoX < 6) {
outcomeTwo = cherry;
} else if (twoX == 6) {
outcomeTwo = luckySeven;
}

if (threeX < 4) {
outcomeThree = apple;
} else if (threeX < 6) {
outcomeThree = cherry;
} else if (threeX == 6) {
outcomeThree = luckySeven;
}

spunSlotOne.src = outcomeOne;
spunSlotTwo.src = outcomeTwo;
spunSlotThree.src = outcomeThree;

document.body.removeChild(slotOne);
document.body.removeChild(slotTwo);
document.body.removeChild(slotThree);

document.body.appendChild(spunSlotOne);
document.body.appendChild(spunSlotTwo);
document.body.appendChild(spunSlotThree);


if (outcomeOne == apple && outcomeTwo == apple && outcomeThree == apple) {
balance += betAmount * 5;
document.getElementById("showBalance").innerHTML = "Money = $" + balance;
winAmount = betAmount * 5;
document.getElementById("showWinAmount").innerHTML = "You win $" + winAmount;
	} else if (outcomeOne == cherry && outcomeTwo == cherry && outcomeThree == cherry) {
balance += betAmount * 25;
document.getElementById("showBalance").innerHTML = "Money = $" + balance;
winAmount = betAmount * 25;
document.getElementById("showWinAmount").innerHTML = "You win $" + winAmount;
	} else if (outcomeOne == luckySeven && outcomeTwo == luckySeven && outcomeThree == luckySeven) {
balance += betAmount * 50;
document.getElementById("showBalance").innerHTML = "Money = $" + balance;
winAmount = betAmount * 50;
document.getElementById("showWinAmount").innerHTML = "You win $" + winAmount;
	} else if (outcomeOne == cherry && outcomeTwo == cherry || outcomeTwo == cherry && outcomeThree == cherry) {
balance += betAmount * 2;
document.getElementById("showBalance").innerHTML = "Money = $" + balance;
winAmount = betAmount * 2;
document.getElementById("showWinAmount").innerHTML = "You win $" + winAmount;
	} else if (outcomeOne == luckySeven && outcomeTwo == luckySeven || outcomeTwo == luckySeven && outcomeThree == luckySeven) {
balance += betAmount * 10;
document.getElementById("showBalance").innerHTML = "Money = $" + balance;
winAmount = betAmount * 10;
document.getElementById("showWinAmount").innerHTML = "You win $" + winAmount;
	} else {
document.getElementById("showWinAmount").innerHTML = "Try again";
}

}





function resetFunction() {

document.body.removeChild(spunSlotOne);
document.body.removeChild(spunSlotTwo);
document.body.removeChild(spunSlotThree);

document.body.appendChild(slotOne);
document.body.appendChild(slotTwo);
document.body.appendChild(slotThree);
}




</script>
<h1 id="showWinAmount"></h1>
<p id="winCombinations"></p>
<script>

document.getElementById("winCombinations").innerHTML = "Win Combinations per $1 Bet:<br>3 Apples = $5<br>2 Cherries = $2<br>3 Cherries = $25<br>2 Lucky Sevens = $10<br>3 Lucky Sevens = $50";



</script>
</html>
