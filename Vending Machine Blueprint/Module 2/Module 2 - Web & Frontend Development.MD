## Web & Frontend Development

1: **The Plain English UI Blueprint**
In the backend module, the computer only had to "think" about numbers and text. On the frontend, the computer has to 
draw the vending machine on a screen and wait for a user to interact with it physically.

To build a website, three distinct layers must work together:

	1. The Blueprint (HTML): "Put a box here. Put a heading inside it. Put a text input box below that, and a button at the 
	   very bottom."

	2. The Style (CSS): "Make the box gray, put 20 pixels of space around the text, make the font clean, and color the button 
	   green."

	3. The Brains (JavaScript/TypeScript): "Watch that button. When a user clicks it, grab the number they typed into the 
	   text input box, do the math, and change the message on the screen."
	   
2: **The Core Web Languages (HTML & CSS)**
Unlike the backend, HTML and CSS work together in the exact same file (or side-by-side) to build what the user sees.

**File: vending.html**

<!DOCTYPE html>
<html>
<head>
    <title>Web Vending Machine</title>
    
    <style>
        .machine-box {
            background-color: #f4f4f4;
            border: 2px solid #333;
            padding: 20px;
            width: 300px;
            border-radius: 8px;
        }
        .btn-dispense {
            background-color: green;
            color: white;
            padding: 10px;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <div class="machine-box">
        <h2>Soda Machine ($1.50)</h2>
        
        <p>Enter your money:</p>
        <input type="number" id="moneyInput" placeholder="0.00">
        
        <button id="dispenseBtn" class="btn-dispense">Insert & Buy</button>
        
        <h3 id="displayMessage"></h3>
    </div>

</body>
</html>

3: **The Interactive Brains (JavaScript & TypeScript)**
Now that the visual machine is drawn on the screen, we add the logic.

	1. **JavaScript (The Web's Muscle)**
			JavaScript hooks directly into the HTML elements we just made using their "IDs" (like moneyInput and 
			dispenseBtn) to read data and make choices.
			
**JavaScript**

	// 1. Remember the price
	const sodaPrice = 1.50;

	// 2. Tell the computer to listen to the green button
	document.getElementById("dispenseBtn").addEventListener("click", function() {
		
		// 3. Grab the number the user typed into the input box
		const userMoney = parseFloat(document.getElementById("moneyInput").value);
		const display = document.getElementById("displayMessage");

		// 4. The exact same decision logic from Module 1!
		if (userMoney >= sodaPrice) {
			display.innerText = "Enjoy your drink! 🎉";
			display.style.color = "green";
		} else {
			display.innerText = "Inadequate funds. ❌";
			display.style.color = "red";
		}
	});


		2. **TypeScript (JavaScript with Guardrails)**
			Look at TypeScript below. It looks almost identical to JavaScript, but notice the extra tags like : number. 
			Microsoft created TypeScript to prevent developers from accidentally putting text into a box meant for numbers, 
			catching bugs before the website goes live.

**TypeScript**
	// 1. Store the price (Strictly locking it down as a number)
	const sodaPrice: number = 1.50;

	document.getElementById("dispenseBtn")?.addEventListener("click", () => {
		
		// 2. We explicitly tell the machine we are pulling data from an Input box
		const inputElement = document.getElementById("moneyInput") as HTMLInputElement;
		const userMoney: number = parseFloat(inputElement.value);
		const display = document.getElementById("displayMessage") as HTMLElement;

		// 3. The Decision
		if (userMoney >= sodaPrice) {
			display.innerText = "Enjoy your drink! 🎉";
		} else {
			display.innerText = "Inadequate funds. ❌";
		}
	});


## The "Plain English" Lesson for Beginners

Lesson 1: **The Trio of Responsibility**
When building for the web, code stops being a single list of instructions. It becomes a team.

	* If you write code in JavaScript but forget the HTML, your logic has no buttons to click.

	* If you write the HTML but forget JavaScript, your webpage is just a dead picture that does nothing when clicked.

Lesson 2: **Event Listeners are just "Triggers"**
In Module 1, the backend programs started running immediately, asked for input, and shut down. Web apps don't do 
that—they sit there silently idling.
JavaScript uses an Event Listener. Think of it like a security guard sitting by a door, waiting for a specific event 
("a mouse click"). The guard sleeps until the click happens, runs the logic, and then goes back to waiting.

Lesson 3: **TypeScript is just "Labeling the Buckets"**
In plain JavaScript, you could accidentally type letters into the money box and crash the calculation. TypeScript forces 
you to declare : number so the computer stops you mid-sentence if you try to pass text where money belongs. 
It is a safety suit built over standard JavaScript.







