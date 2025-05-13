# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.

body {
    font-family: sans-serif;
    text-align: center;
    padding: 50px;
    background-color: #f0f0f0;
}

#box {
    width: 100px;
    height: 100px;
    background-color: coral;
    margin: 30px auto;
    border-radius: 10px;
    position: relative;
}

/* Animation Class */
.bounce {
    animation: bounce 1s ease-out;
}

/* Define the keyframes for bounce */
@keyframes bounce {
    0%   { transform: translateY(0); }
    50%  { transform: translateY(-100px); }
    100% { transform: translateY(0); }
}

Store data in localStorage.
Apply JavaScript to trigger animations.

// Get elements
const box = document.getElementById('box');
const button = document.getElementById('animateBtn');

// Check if animation was triggered before (saved in localStorage)
if (localStorage.getItem('wasAnimated') === 'true') {
    box.classList.add('bounce'); // Play animation once on load
    setTimeout(() => {
        box.classList.remove('bounce');
    }, 1000);
}

// Button click triggers animation
button.addEventListener('click', () => {
    box.classList.add('bounce');

    // Save the animation state
    localStorage.setItem('wasAnimated', 'true');

    // Remove the class after animation to allow re-adding later
    setTimeout(() => {
        box.classList.remove('bounce');
    }, 1000);
});

Happy Coding! 💻✨
