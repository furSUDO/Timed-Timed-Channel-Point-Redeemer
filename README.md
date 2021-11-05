# Timed Timed Channel Point Redeemer
## Browser script to periodically redeem twitch channel point rewards
```js
var rewardName = "Name of Reward"; // Duh?
var delay = 500; // In ms
var loopFor = 1000; // How many times to redeem reward

// Function to redeem rewards
(function pointLoop(i) {
	setTimeout(function() {
    	document.querySelector(`[aria-label="Points Balance"]`).click();
    	document.querySelector(`img[alt=${CSS.escape(rewardName)}]`).click();
    	document.querySelector(`p[data-test-selector="RewardText"]`).click();         
    if (--i) pointLoop(i);   
	}, delay)
})(loopFor);
```