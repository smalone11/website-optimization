# Website Performance Optimization Project

## Running the Application

1. In the *src* directory, open *index.html* in a web browser to see the old portfolio site. Clicking on the last link on the page will open the old version of Cam's Pizzeria.

2. In the *dist* directory, open *index.html* in a web browser to see the new portfolio site. Clicking on the last link will now open to the new version of Cam's Pizzeria.

## Optimizations

#### Critical Rendering Path

1. Moved over the JS code to index.html.
2. Made any non-critical script asynchronous.
3. Added a media attribute to the *print.css* link.
4. Any css in *style.css* that was not used mutliple times was put inline in *index.html*.
5. Any additional css in *style.css* was moved into a style tag in the header of *index.html*.
6. Removed extra, unnecessary *.html* files.
7. Resized and compressed images.

#### Framerate and Computation Efficiency

1. Triggered GPU by adding *transform: translateZ(0)* to *.mover* in *views/style.css*.

2. Moved variables or calculations outside of loops to optimize them.
  1. *changePizzaSizes* function (starts on line 452).
  2. for loop starting on line 479.
  3. *updatePositions* function (starts on line 510).
  4. Event listener starting on line 538.

3. Removed *document.querySelector("")* uses and replaced with *document.getElementById("")* or *document.getElementByClassName("")*.
  1. *changeSliderLabel* function (starts on line 407).
  2. Variable declaration on line 428.
  3. Variable declaration on line 454.
  4. Variable declaration on line 479.
  5. Variable declaration on line 514.
  6. Variable declaration on line 547.

4. In the event listener *DOMContentLoaded* (line 538), changed the value of the variable *s* and changed the number of times the for loop is iterated through. The iterations is based on the number of rows and columns used and rows is based on the users screen height.