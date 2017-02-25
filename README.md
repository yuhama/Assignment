# Assignment

Description
------------------

In this assignment we want you to implement a simple web application that calculates the score during a game of ten pin bowling.

Prerequisities
------------------

- Create a frontend application, ideally an SPA using technologies such as Angular or React
- Create a backend API (No database is required in this assignment).
- Styling should be done in a pre-processor such as Less, Sass or Stylus.
- Browser support should be the newest version of Chrome, Firefox, Safari, and IE11.
- Use a well defined architecture with proper separation of concerns.
- Write tests.

**Structure**

- Contains an API endpoint handler that accepts an array of bowling scores and returns the current score. The handler should accept the frames as a JSON object with the following syntax: `{ "frames": [{"first": 3, "second": 4}, {"first": 10, "second": 0}, ... ] }`. The handler should return the score as a JSON object with the following syntax: `{ "score": 7 }`.

- Displays input elements that enables the user to enter the result of one round. You can for example use two input elements of type text, one for each roll, and a submit button for submitting scores.

- Bind an event handler to the input element or a submit button that posts the current rounds to the action method on the server. For this assignment, you can let the browser keep track of all rounds so far. There's no need to store any state on the server.

- When a resulting score is returned it should be displayed somewhere on the current page along with the result for each round played.

- When the user enters the result for another round, send all played rounds so far to the action method.

**Example scenario**

Player starts a new game by visiting the web site:

The current score is 0.

Player rolls a 3 and a 4:
    The user enters 3 and 4 and submits the score.
	The web browser makes an AJAX call to an action method on the web server: `{"frames": [{"first": 3, "second": 4}]}`
	The web server responds with: `{"score": 7}`
	The web browser displays the current score.

Player rolls a 4 and 5:
	The web browser sends: `["frames": {"first":3, "second": 4}, {"first": 4, "second": 5}]`
	The web server responds: `{"score": 16}`

etc.

**Rules of bowling**

* A game consists of ten frames. Frame 1-9 are composed of two rolls. Frame 10 can be composed of up to three rolls depending on if the first rolls in the frame is a strike or a spare.

* Each frame can have one of three marks:
  - Strike: all 10 pins where knocked down with the first roll.
  - Spare: all 10 pins where knocked down using two rolls.
  - Open: some pins where left standing after the frame was completed.

* When calculating the total score, the sum of the score for each frame is used. 
  - For an open frame the score is the total number of pins knocked down. 
  - For a strike, the score is 10 + the sum of the two rolls in the following frame.
  - For a spare, the score is 10 + the number of pins knocked down in the first roll of the following frame.

 The tenth frame may be composed of up to three rolls: the bonus roll(s) following a strike or spare in the tenth (sometimes referred to as the eleventh and twelfth frames) are fill ball(s) used only to calculate the score of the mark rolled in the tenth.

**Deadline**

You have 72 hours to complete the assignment.

**Last words**

Keep the code clean with a clear architecture where the code is easy to read, and to test.

Don't forget tests.

Good luck and have fun!
