
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AGASOBANUYE WATCHNEXT</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #101010;
  color: white;
  font-family: Arial, sans-serif;
}

header {
  background: #080808;
  padding: 20px 6%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 15px;
}

.logo {
  color: gold;
  font-size: 23px;
  font-weight: bold;
}

nav a {
  color: white;
  text-decoration: none;
  margin: 10px;
}

nav a:hover {
  color: gold;
}

.hero {
  padding: 85px 7%;
  background: linear-gradient(90deg, #111, #594000);
}

.hero h1 {
  font-size: 42px;
  margin-bottom: 15px;
}

.hero p {
  color: #ddd;
  margin-bottom: 25px;
}

button {
  background: gold;
  color: black;
  border: none;
  padding: 12px 20px;
  border-radius: 5px;
  cursor: pointer;
  font-weight: bold;
}

button:hover {
  background: orange;
}

.search-area {
  padding: 25px 7% 0;
}

input, select {
  padding: 13px;
  border-radius: 5px;
  border: none;
  margin: 5px;
  font-size: 15px;
}

#search {
  width: min(100%, 400px);
}

section {
  padding: 35px 7%;
}

h2 {
  color: gold;
  margin-bottom: 22px;
}

.movies {
  display: grid;
  grid-template-columns: repeat(
    auto-fit, minmax(190px, 1fr)
  );
  gap: 22px;
}

.movie {
  background: #202020;
  border-radius: 10px;
  overflow: hidden;
  transition: 0.3s;
}

.movie:hover {
  transform: translateY(-5px);
}

.poster {
  height: 210px;
  background: linear-gradient(135deg, #614900, #111);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 55px;
  color: gold;
}

.movie-content {
  padding: 15px;
}

.movie h3 {
  margin-bottom: 9px;
}

.movie p {
  color: #bbb;
  font-size: 14px;
  margin-bottom: 9px;
}

.movie button {
  margin-top: 8px;
  width: 100%;
}

.category {
  display: inline-block;
  color: gold;
  font-size: 12px;
  margin-bottom: 8px;
}

.about {
  background: #191919;
  line-height: 1.8;
}

.about p {
  color: #ccc;
}

footer {
  background: #080808;
  padding: 30px;
  text-align: center;
  color: #aaa;
  line-height: 2;
}

footer a {
  color: gold;
}

.modal {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,.85);
  justify-content: center;
  align-items: center;
  padding: 20px;
  z-index: 10;
}

.modal-content {
  background: #222;
  padding: 30px;
  border-radius: 10px;
  max-width: 450px;
  width: 100%;
}

.modal-content h2 {
  margin-bottom: 15px;
}

.modal-content p {
  color: #ddd;
  line-height: 1.7;
  margin-bottom: 18px;
}

.close {
  float: right;
  background: #444;
  color: white;
}

.no-results {
  color: #bbb;
  padding: 20px 0;
  display: none;
}

@media(max-width:600px) {
  header {
    justify-content: center;
  }

  .hero h1 {
    font-size: 30px;
  }

  nav {
    text-align: center;
  }
}
</style>
</head>

<body>

<!-- HEADER -->
<header>
  <div class="logo">🎬 AGASOBANUYE WATCHNEXT</div>

  <nav>
    <a href="#home">Home</a>
    <a href="#movies">Movies</a>
    <a href="#about">About</a>
  </nav>
</header>

<!-- HOME -->
<div class="hero" id="home">
  <h1>Discover Your Next Movie</h1>
  <p>
    Welcome to AGASOBANUYE WATCHNEXT.
    Find your favourite Agasobanuye movies.
  </p>

  <a href="#movies">
    <button>Explore Movies</button>
  </a>
</div>

<!-- SEARCH -->
<div class="search-area">
  <input
    type="text"
    id="search"
    placeholder="Search movies..."
    oninput="filterMovies()"
  >

  <select id="category" onchange="filterMovies()">
    <option value="all">All Categories</option>
    <option value="Action">Action</option>
    <option value="Drama">Drama</option>
    <option value="Romance">Romance</option>
    <option value="Comedy">Comedy</option>
    <option value="Indian">Indian</option>
    <option value="Adventure">Adventure</option>
  </select>
</div>

<!-- MOVIES -->
<section id="movies">
  <h2>Popular Movies</h2>

  <div class="movies" id="movieList">

    <div class="movie"
      data-title="Enemy at the Gates"
      data-category="Action"
      data-description="An exciting war and action movie.">

      <div class="poster">🎬</div>
      <div class="movie-content">
        <span class="category">ACTION</span>
        <h3>Enemy at the Gates</h3>
        <p>Action and adventure.</p>
        <button onclick="showDetails(this)">
          View Details
        </button>
      </div>
    </div>

    <div class="movie"
      data-title="Fast and Furious 8"
      data-category="Action"
      data-description="An action movie featuring exciting car adventures.">

      <div class="poster">🏎️</div>
      <div class="movie-content">
        <span class="category">ACTION</span>
        <h3>Fast and Furious 8</h3>
        <p>Speed and adventure.</p>
        <button onclick="showDetails(this)">
          View Details
        </button>
      </div>
    </div>

    <div class="movie"
      data-title="Pihu"
      data-category="Indian"
      data-description="An Indian drama film.">

      <div class="poster">⭐</div>
      <div class="movie-content">
        <span class="category">INDIAN</span>
        <h3>Pihu</h3>
        <p>Indian drama.</p>
        <button onclick="showDetails(this)">
          View Details
        </button>
      </div>
    </div>

    <div class="movie"
      data-title="Love Story"
      data-category="Romance"
      data-description="A romantic movie about relationships.">

      <div class="poster">❤️</div>
      <div class="movie-content">
        <span class="category">ROMANCE</span>
        <h3>Love Story</h3>
        <p>Romantic entertainment.</p>
        <button onclick="showDetails(this)">
          View Details
        </button>
      </div>
    </div>

    <div class="movie"
      data-title="Funny Family"
      data-category="Comedy"
      data-description="A comedy movie for entertainment.">

      <div class="poster">😂</div>
      <div class="movie-content">
        <span class="category">COMEDY</span>
        <h3>Funny Family</h3>
        <p>Enjoy some laughter.</p>
        <button onclick="showDetails(this)">
          View Details
        </button>
      </div>
    </div>

    <div class="movie"
      data-title="Adventure World"
      data-category="Adventure"
      data-description="An exciting adventure story.">

      <div class="poster">🌍</div>
      <div class="movie-content">
        <span class="category">ADVENTURE</span>
        <h3>Adventure World</h3>
        <p>Discover a new world.</p>
        <button onclick="showDetails(this)">
          View Details
        </button>
      </div>
    </div>

  </div>

  <p class="no-results" id="noResults">
    No movies found. Try another search.
  </p>
</section>

<!-- OSHAKUR LINK -->
<section style="text-align:center;background:#191919">
  <h2>Explore More Movies</h2>

  <p style="color:#ccc;margin-bottom:20px">
    Discover more movies from OSHAkur Films.
  </p>

  <a href="https://www.oshakurfilms.com/"
     target="_blank"
     rel="noopener noreferrer">
    <button>Visit OSHAkur Films</button>
  </a>
</section>

<!-- ABOUT -->
<section class="about" id="about">
  <h2>About WatchNext</h2>

  <p>
    AGASOBANUYE WATCHNEXT is a movie discovery
    platform designed to help visitors find
    interesting movies, explore categories and
    read movie descriptions.
  </p>

  <p>
    Our goal is to make discovering movies
    easier and more enjoyable.
  </p>
</section>

<!-- DETAILS MODAL -->
<div class="modal" id="modal">
  <div class="modal-content">

    <button class="close" onclick="closeModal()">
      Close
    </button>

    <h2 id="modalTitle">Movie Title</h2>

    <p id="modalDescription"></p>

    <a href="https://www.oshakurfilms.com/"
       target="_blank"
       rel="noopener noreferrer">
      <button>Explore on OSHAkur</button>
    </a>

  </div>
</div>

<!-- FOOTER -->
<footer>
  <h3 style="color:gold">
    AGASOBANUYE WATCHNEXT
  </h3>

  <p>Discover. Explore. WatchNext.</p>

  <p>© 2026 AGASOBANUYE WATCHNEXT</p>

  <p>
    Movie information and external links
    belong to their respective owners.
  </p>
</footer>

<!-- JAVASCRIPT -->
<script>

function filterMovies() {

  let search = document
    .getElementById("search")
    .value.toLowerCase();

  let category = document
    .getElementById("category")
    .value;

  let movies = document.querySelectorAll(".movie");

  let count = 0;

  movies.forEach(movie => {

    let title = movie.dataset.title.toLowerCase();

    let movieCategory = movie.dataset.category;

    let matchesSearch = title.includes(search);

    let matchesCategory =
      category === "all" ||
      movieCategory === category;

    if (matchesSearch && matchesCategory) {
      movie.style.display = "block";
      count++;
    } else {
      movie.style.display = "none";
    }

  });

  document.getElementById("noResults").style.display =
    count === 0 ? "block" : "none";
}

function showDetails(button) {

  let movie = button.closest(".movie");

  document.getElementById("modalTitle").textContent =
    movie.dataset.title;

  document.getElementById("modalDescription").textContent =
    movie.dataset.description;

  document.getElementById("modal").style.display =
    "flex";
}

function closeModal() {

  document.getElementById("modal").style.display =
    "none";
}

window.onclick = function(event) {

  let modal = document.getElementById("modal");

  if (event.target === modal) {
    closeModal();
  }

}

</script>

</body>
</html>
