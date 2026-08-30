# Tic-Tac-Toe --- Scorepad

A browser-based Tic-Tac-Toe game built with **HTML, CSS, and vanilla
JavaScript**.

The game provides both two-player and single-player modes, with an
optional unbeatable computer opponent powered by the minimax algorithm.
It combines a score-tracking system with a paper scorepad-inspired
interface.

## Features

-   Two-player mode
-   Player vs Computer mode
-   Easy computer difficulty
-   Unbeatable computer difficulty using minimax
-   Persistent match score during the current session
-   Draw tracking
-   New Round functionality
-   Reset Scores functionality
-   Visual indication of the current player's turn
-   Winning-cell highlighting
-   Animated winning line
-   Hand-drawn-style X and O marks
-   Responsive layout
-   Keyboard focus indicators
-   Reduced-motion support through `prefers-reduced-motion`

## Game Modes

### 2 Players

Two players take turns playing on the same device:

-   Player X starts the round.
-   Players alternate between X and O.
-   The first player to complete a winning line wins.
-   If all nine cells are filled without a winner, the round ends in a
    draw.

### Vs Computer

Player X plays against the computer as Player O.

When this mode is selected, two difficulty levels become available:

#### Easy

The computer selects a random available cell.

#### Unbeatable

The computer uses the **minimax algorithm** to evaluate possible moves
and select the optimal move.

With the current implementation, the hard difficulty is designed so that
the computer cannot be defeated through normal play.

## Rules

A player wins by placing three of their marks in a row:

-   Horizontal
-   Vertical
-   Diagonal

There are eight possible winning combinations:

``` text
[0,1,2]  [3,4,5]  [6,7,8]
[0,3,6]  [1,4,7]  [2,5,8]
[0,4,8]  [2,4,6]
```

If all nine cells are occupied and no winning combination is completed,
the round is recorded as a draw.

## Game Logic

The board is represented by a nine-element array. Each position
corresponds to one cell on the board.

The application:

1.  Initializes an empty board.
2.  Sets Player X as the starting player.
3.  Accepts a move when an available cell is selected.
4.  Checks the board for a winning combination after every move.
5.  Ends the round if a player wins or the board is full.
6.  Updates the appropriate score.
7.  Switches the active player when the game continues.

The game maintains separate scores for:

-   Player X
-   Player O / Computer
-   Draws

## Computer AI

The hard difficulty uses the **minimax algorithm**.

The algorithm recursively evaluates possible future board states:

-   Computer wins receive a positive score.
-   Player wins receive a negative score.
-   Draws receive a neutral score.
-   Earlier wins are preferred through depth-based scoring.

The computer evaluates available moves and chooses the move with the
highest resulting score.

This provides an optimal Tic-Tac-Toe opponent rather than relying on
random move selection.

## Interface

The application uses a scorepad-inspired visual design with:

-   Dark blue console-style container
-   Cream paper game board
-   Hand-drawn grid lines
-   Animated X and O strokes
-   Gold winning-line indicator
-   Separate colors for X and O
-   Scoreboard for wins and draws
-   Mode and difficulty selectors
-   Turn status indicator

The interface uses **Kalam** for the handwritten-style display text and
**Space Mono** for the interface and scoreboard typography.

## Technologies

-   HTML5
-   CSS3
-   Vanilla JavaScript
-   SVG
-   Google Fonts

No frameworks, build tools, or external JavaScript libraries are
required.

## Project Structure

``` text
.
├── tictactoee.html
└── README.md
```

The complete game is contained in `tictactoee.html`, including the HTML
structure, CSS styling, SVG graphics, game state, scoring system,
computer AI, and event handling.

## Running Locally

No installation or build process is required.

### Directly in a Browser

Clone or download the repository and open:

``` text
tictactoee.html
```

in any modern web browser.

### Using a Local Server

From the project directory, run:

``` bash
python -m http.server
```

Then open the local address provided by the server in your browser.

## Controls

### Game Controls

-   **2 Players** --- switches to local two-player mode.
-   **Vs Computer** --- enables single-player mode.
-   **Easy** --- selects random computer moves.
-   **Unbeatable** --- selects minimax-based computer moves.
-   **New Round** --- starts a new round while keeping the current
    scores.
-   **Reset Scores** --- clears all scores and starts a new round.

## Score Tracking

Scores are maintained during the current browser session.

  Score                 Description
  --------------------- -------------------------------------------
  Player X              Number of rounds won by X
  Player O / Computer   Number of rounds won by O or the computer
  Draws                 Number of rounds ending without a winner

Changing game mode starts a new round but does not reset the existing
scores.

## Accessibility

The interface includes several accessibility-focused behaviors:

-   Visible `:focus-visible` outlines for interactive controls
-   Semantic button controls for board cells
-   ARIA labels for individual board cells
-   Reduced-motion support for users who prefer less animation

## Browser Compatibility

The project is intended for modern browsers supporting standard HTML5,
CSS3, JavaScript, and SVG functionality.

## Possible Future Improvements

-   Persistent scores using `localStorage`
-   Match history
-   Player name customization
-   Sound effects
-   Additional AI difficulty levels
-   AI move statistics
-   Best-of-3 and Best-of-5 match modes
-   Online multiplayer
-   Custom board sizes
-   Mobile-specific interaction improvements

## License

No license is currently specified for this project. If the repository
will be publicly distributed or reused by others, an appropriate
open-source license should be added.

------------------------------------------------------------------------

A lightweight Tic-Tac-Toe implementation using HTML, CSS, JavaScript,
SVG, and the minimax algorithm.
