01. Web & Frontend Development Lesson

What You Will Learn
	•	The Plain English UI Blueprint: How HTML, CSS, and JavaScript/TypeScript team up on a web page. 
	•	HTML & CSS basics (vending.html & style.css): Putting input boxes, buttons, and messages on screen and styling them. 
	•	JavaScript event listeners (vending.js): Hooking onto element IDs and waiting for a button click to run the $1.50 check. 
	•	TypeScript guardrails (vending.ts): Using type labels like : number to catch data-type mistakes early. 

1. The Plain English UI Blueprint

On the frontend, the computer has to draw the vending machine on a screen and wait for a user to interact with it physically. 
To build a website, three distinct layers must work together: 
	1.	The Blueprint (HTML): "Put a box here. Put a heading inside it. Put a text input box below that, and a button at the very bottom." 
	2.	The Style (CSS): "Make the box gray, put 20 pixels of space around the text, make the font clean, and color the button green." 
	3.	The Brains (JavaScript/TypeScript): "Watch that button. When a user clicks it, grab the number they typed into the text input box, do the math, and change the message on the screen." 
	2. The Core Web Languages (HTML & CSS)
Unlike the backend, HTML and CSS work together to build what the user sees. 

File: vending.html
		<p>Enter your money:</p>
		<input type="number" id="moneyInput" placeholder="0.00">
		
		<button id="dispenseBtn" class="btn-dispense">Insert & Buy</button>
		
		<h3 id="displayMessage"></h3>

3. Interactive Logic (JavaScript & TypeScript)

JavaScript (The Web's Muscle)
JavaScript hooks directly into the HTML elements we just made using their "IDs" (like moneyInput and dispenseBtn) to read data and make choices. 

		// 1. Remember the price
		const sodaPrice = 1.50;
		
		// 2. Tell the computer to listen to the green button
		document.getElementById("dispenseBtn").addEventListener("click", function() {
		  // 3. Grab the number the user typed into the input box
		  const userMoney = parseFloat(document.getElementById("moneyInput").value);
		  const display = document.getElementById("displayMessage");
		
		  // 4. The exact same decision logic!
		  if (userMoney >= sodaPrice) {
		    display.innerText = "Enjoy your drink! 🎉";
		    display.style.color = "green";
		  } else {
		    display.innerText = "Inadequate funds. ❌";
		    display.style.color = "red";
		  }
		});

TypeScript (JavaScript with Guardrails)
Look at TypeScript below. It looks almost identical to JavaScript, but notice the extra tags like : number. Microsoft created TypeScript to prevent developers from accidentally putting text into a box meant for numbers, catching bugs before the website goes live. 

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

4. The "Plain English" Lessons for Beginners

	•	Lesson 1: The Trio of Responsibility — When building for the web, code stops being a single list of instructions and becomes a team. If you write code in JavaScript but forget the HTML, your logic has no buttons to click. If you write the HTML but forget JavaScript, your webpage is just a dead picture that does nothing when clicked. 
	•	Lesson 2: Event Listeners are just "Triggers" — Web apps sit there silently idling and use an Event Listener. Think of it like a security guard sitting by a door, waiting for a specific event ("a mouse click"). The guard sleeps until the click happens, runs the logic, and then goes back to waiting. 
	•	Lesson 3: TypeScript is just "Labeling the Buckets" — In plain JavaScript, you could accidentally type letters into the money box and crash the calculation. TypeScript forces you to declare : number so the computer stops you mid-sentence if you try to pass text where money belongs. It is a safety suit built over standard JavaScript. 
