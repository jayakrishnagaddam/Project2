<!-- ✅ HEADER with Logo, Search and Navigation -->
<header class="header">
  <a routerLink="/user-home" class="logo">TrackFit</a>

  <!-- 🔍 Search in Navbar -->
  <div class="navbar-search">
    <input type="text"
           [(ngModel)]="searchQuery"
           class="navbar-search-input"
           placeholder="Search workouts..." />
  </div>

  <nav class="nav-links">
    <a routerLink="/remainder">Remainder</a>
    <a routerLink="/profile">Profile</a>
  </nav>

</header>

<!-- ✅ DASHBOARD CONTENT -->
<div class="dashboard-container">

  <!-- 🔘 Category Filters -->
  <div class="category-filter">
    <button *ngFor="let category of categories"
            [class.active]="selectedCategory === category"
            (click)="setCategory(category)">
      {{ category }}
    </button>
  </div>

  <!-- 🏋️ Workout Cards -->
  <div class="cards-container">
    <div class="workout-card"
         *ngFor="let workout of filteredWorkouts"
         (click)="onCardClick(workout)"
         [class.expanded]="selectedWorkout === workout">

      <img [src]="workout.image" alt="{{ workout.name }}" class="workout-image" />
      <h3>{{ workout.name }}</h3>
      <p>Category: {{ workout.category }}</p>
      <p>Duration: {{ workout.duration }}</p>

      <!-- 📘 Show instructions only if this card is selected -->
      <div class="instructions" *ngIf="selectedWorkout === workout">
        <h4>Instructions:</h4>
        <ul>
          <li *ngFor="let step of workout.instructions">{{ step }}</li>
        </ul>
      </div>
    </div>
  </div>
</div>

<!-- ✅ FOOTER -->
<footer class="footer">
  <p>
    <a href="#">Contact Us</a> | <a href="#">Feedback</a>
  </p>
</footer>



/* === Global Reset === */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}


body {
  font-family: 'Segoe UI', sans-serif;
  background-color: #f9fafc;
}
/* === Header/Navbar === */
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 16px 32px;
  background: linear-gradient(to right, #1e1e2f, #2c2c54);
  color: white;
  flex-wrap: wrap;
  gap: 10px;
  position: sticky;
  top: 0;
  z-index: 100;
}

.logo {
  font-size: 24px;
  font-weight: bold;
  color: white;
  text-decoration: none;
  cursor: pointer;
}

/* Navbar Search */
.navbar-search {
  flex: 1;
  max-width: 300px;
}

.navbar-search-input {
  width: 100%;
  padding: 8px 16px;
  border-radius: 20px;
  border: none;
  font-size: 14px;
  outline: none;
  background-color: white;
  color: #333;
  transition: box-shadow 0.3s ease;
}

  .navbar-search-input:focus {
    box-shadow: 0 0 0 2px #00bcd4;
  }

/* Navigation links */
.nav-links {
  display: flex;
  gap: 16px;
}

  .nav-links a {
    color: white;
    text-decoration: none;
    font-size: 16px;
    transition: color 0.3s ease;
  }

    .nav-links a:hover {
      color: #ffcc00;
    }

/* === Dashboard Container === */
.dashboard-container {
  padding: 2rem;
  min-height: 100vh;
}

/* === Category Filter Buttons === */
.category-filter {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-bottom: 20px;
  justify-content: center;
}

  .category-filter button {
    padding: 10px 18px;
    background-color: #eeeeee;
    border: 2px solid #1e1e2f;
    border-radius: 20px;
    font-size: 14px;
    cursor: pointer;
    transition: background-color 0.3s ease, transform 0.2s ease;
  }

    .category-filter button:hover {
      background-color: darkslategrey;
      color: white;
    }

    .category-filter button.active {
      background-color: #1e1e2f;
      color: white;
      font-weight: bold;
      transform: scale(1.05);
    }

/* === Cards === */
.cards-container {
  display: flex;
  flex-wrap: wrap;
  gap: 1.5rem;
  justify-content: center;
}

.workout-card {
  background: #ffffff;
  border-left: 5px solid #1e1e2f;
  border-radius: 12px;
  padding: 1rem;
  width: 300px;
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s ease, background-color 0.3s ease, border-color 0.3s ease;
  text-align: center;
  cursor: pointer;
  position: relative;
}

  .workout-card:hover {
    transform: translateY(-5px);
    border-left-color:aquamarine;
  }

  .workout-card.expanded {
    background-color: #e3f2fd;
    border-left-color: aquamarine;
  }

.workout-image {
  width: 100%;
  height: 160px;
  object-fit: cover;
  border-radius: 8px;
  margin-bottom: 12px;
}

/* Instructions inside expanded card */
.instructions {
  margin-top: 1rem;
  text-align: left;
  max-height: 200px;
  overflow-y: auto;
}

  .instructions h4 {
    margin-bottom: 0.5rem;
    color: #1976d2;
  }

  .instructions ul {
    padding-left: 20px;
    list-style-type: disc;
  }

  .instructions li {
    margin-bottom: 6px;
    color: #444;
  }

/* === Footer === */
.footer {
  background-color: #1e1e2f;
  color: white;
  text-align: center;
  padding: 16px;
  position: relative;
  bottom: 0;
  width: 100%;
}

  .footer a {
    color: #ffcc00;
    text-decoration: none;
    margin: 0 10px;
  }

    .footer a:hover {
      text-decoration: underline;
    }

/* === Responsive === */
@media (max-width: 768px) {
  .cards-container {
    flex-direction: column;
    align-items: center;
  }

  .header {
    flex-direction: column;
    align-items: flex-start;
  }

  .nav-links {
    justify-content: center;
    width: 100%;
    margin-top: 10px;
  }

  .navbar-search {
    width: 100%;
    margin: 10px 0;
  }

  .category-filter {
    justify-content: center;
  }
}
