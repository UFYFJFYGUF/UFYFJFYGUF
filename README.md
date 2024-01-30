// Fitness Tips & Promotion App

// Create sprites
let backgroundSprite = createSprite(200, 200);
backgroundSprite.setAnimation("background");
backgroundSprite.width = 400;
backgroundSprite.height = 400;

let titleText = createSprite(200, 50);
titleText.setAnimation("title");
titleText.scale = 0.8;

let tipText = createSprite(200, 150);
tipText.setAnimation("tip");
tipText.scale = 0.8;

let promotionSprite = createSprite(200, 300);
promotionSprite.setAnimation("promotion");
promotionSprite.scale = 0.8;

// Array of fitness tips
let fitnessTips = [
  "Drink plenty of water.",
  "Get at least 7 hours of sleep.",
  "Include fruits and vegetables in your diet.",
  "Do 30 minutes of exercise daily.",
  "Practice good posture.",
  "Take breaks from screen time.",
];

// Function to display a random fitness tip
function displayRandomTip() {
  let randomIndex = Math.floor(Math.random() * fitnessTips.length);
  tipText.setAnimation(fitnessTips[randomIndex]);
}

// Main program loop
function draw() {
  background("white");

  // Display title
  drawSprite(titleText);

  // Display tip
  drawSprite(tipText);

  // Display promotion
  drawSprite(promotionSprite);

  // Change tip every 5 seconds
  if (frameCount % 300 === 0) {
    displayRandomTip();
  }
}
