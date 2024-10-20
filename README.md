# prodigy-
HTML CODE
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Summer Drinks</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <!-- Navigation Bar -->
  <nav>
    <div class="container">
      <h1 class="logo">Summer Drinks</h1>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Drinks</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </div>
  </nav>

  <!-- Hero Section -->
  <section class="hero">
    <div class="container">
      <h1>Cool Down with Refreshing Summer Drinks</h1>
      <p>Discover the best summer drinks to quench your thirst!</p>
      <a href="#drinks" class="btn">Explore Drinks</a>
    </div>
  </section>

  <!-- Featured Drinks Section -->
  <section id="drinks" class="drinks">
    <div class="container">
      <h2>Featured Drinks</h2>
      <div class="drink-cards">
        <div class="drink-card">
          <img src="https://via.placeholder.com/150" alt="Lemonade">
          <h3>Lemonade</h3>
          <p>Freshly squeezed lemons for the perfect tangy taste.</p>
        </div>
        <div class="drink-card">
          <img src="https://via.placeholder.com/150" alt="Iced Tea">
          <h3>Iced Tea</h3>
          <p>Cool and refreshing with a hint of mint.</p>
        </div>
        <div class="drink-card">
          <img src="https://via.placeholder.com/150" alt="Mango Smoothie">
          <h3>Mango Smoothie</h3>
          <p>A tropical treat with ripe mangoes and yogurt.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer>
    <div class="container">
      <p>&copy; 2024 Summer Drinks. All rights reserved.</p>
    </div>
  </footer>

</body>
</html>
CSS CODE
/* General Styling */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Arial', sans-serif;
  line-height: 1.6;
}

.container {
  width: 90%;
  margin: 0 auto;
  max-width: 1200px;
}

/* Navigation Bar */
nav {
  background-color: #ff6b6b;
  color: white;
  padding: 1em 0;
}

nav .logo {
  font-size: 1.5em;
  text-transform: uppercase;
}

nav ul {
  list-style: none;
  display: flex;
  justify-content: space-around;
}

nav ul li a {
  color: white;
  text-decoration: none;
  font-weight: bold;
  padding: 10px 20px;
}

nav ul li a:hover {
  background-color: #ff4c4c;
  border-radius: 5px;
}

/* Hero Section */
.hero {
  background: url('https://via.placeholder.com/1200x600') no-repeat center center/cover;
  color: white;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.hero h1 {
  font-size: 3em;
  margin-bottom: 0.5em;
}

.hero p {
  font-size: 1.2em;
  margin-bottom: 1em;
}

.hero .btn {
  background-color: #ff6b6b;
  color: white;
  padding: 10px 20px;
  text-decoration: none;
  font-weight: bold;
  border-radius: 5px;
}

.hero .btn:hover {
  background-color: #ff4c4c;
}

/* Drinks Section */
.drinks {
  padding: 2em 0;
  text-align: center;
}

.drinks h2 {
  font-size: 2.5em;
  margin-bottom: 1em;
}

.drink-cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.drink-card {
  background-color: #fff;
  padding: 1em;
  margin: 1em;
  width: 30%;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.drink-card:hover {
  transform: scale(1.05);
}

.drink-card img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.drink-card h3 {
  font-size: 1.5em;
  margin: 0.5em 0;
}

.drink-card p {
  font-size: 1em;
  color: #333;
}

/* Footer */
footer {
  background-color: #ff6b6b;
  color: white;
  text-align: center;
  padding: 1em 0;
}

/* Responsive Design */
@media (max-width: 768px) {
  .drink-card {
    width: 45%;
  }
}

@media (max-width: 576px) {
  .drink-card {
    width: 100%;
  }
}
JAVA SCRIPT CODE
// JavaScript for the carousel functionality

const carousel = document.querySelector('.carousel');
const items = document.querySelectorAll('.carousel-item');
const prevButton = document.getElementById('prev');
const nextButton = document.getElementById('next');

let currentIndex = 0;

// Move carousel to the right (next)
nextButton.addEventListener('click', () => {
  if (currentIndex < items.length - 1) {
    currentIndex++;
  } else {
    currentIndex = 0; // Loop back to the start
  }
  updateCarousel();
});

// Move carousel to the left (previous)
prevButton.addEventListener('click', () => {
  if (currentIndex > 0) {
    currentIndex--;
  } else {
    currentIndex = items.length - 1; // Loop to the end
  }
  updateCarousel();
});

// Function to update the position of the carousel
function updateCarousel() {
  const itemWidth = items[0].offsetWidth;
  carousel.style.transform = `translateX(-${currentIndex * itemWidth}px)`;
}

// Smooth scrolling for navigation
document.querySelectorAll('nav ul li a').forEach(anchor => {
  anchor.addEventListener('click', function (e) {
    e.preventDefault();
    document.querySelector(this.getAttribute('href')).scrollIntoView({
      behavior: 'smooth'
    });
  });
});

