# Project2

/* Reset and base */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Segoe UI', sans-serif;
  background-color: #f9fafc;
  color: #222;
  line-height: 1.6;
}

/* HEADER */
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 32px;
  background: linear-gradient(to right, #1e1e2f, #2c2c54);
  color: white;
  position: sticky;
  top: 0;
  z-index: 1000;
  box-shadow: 0 4px 8px rgba(0,0,0,0.15);
}

.logo {
  font-size: 26px;
  font-weight: bold;
  color: white;
  text-decoration: none;
  cursor: pointer;
}

.header-icons {
  display: flex;
  align-items: center;
  gap: 16px;
}

.notification-icon {
  color: #ffeb3b;
  font-size: 22px;
  text-decoration: none;
  transition: color 0.3s ease;
}

  .notification-icon:hover {
    color: #fff700;
  }

.profile-icon img {
  width: 36px;
  height: 36px;
  border-radius: 50%;
  border: 2px solid #00e5ff;
  cursor: pointer;
  transition: transform 0.3s ease;
}

  .profile-icon img:hover {
    transform: scale(1.1);
  }

/* HERO SECTION */
.hero-section {
  background: url('/assets/images/fitness-bg.jpg') no-repeat center center/cover;
  height: 90vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  color: #fff;
  padding: 20px;
}

.hero-content {
  background-color: rgba(0, 0, 0, 0.6);
  padding: 40px;
  border-radius: 12px;
  max-width: 600px;
  animation: fadeInUp 1s ease-out;
}

  .hero-content h1 {
    font-size: 3rem;
    margin-bottom: 20px;
  }

  .hero-content p {
    font-size: 1.25rem;
    line-height: 1.6;
    margin-bottom: 25px;
  }

.btn-primary {
  background: #00e5ff;
  color: #000;
  padding: 12px 24px;
  border-radius: 25px;
  text-decoration: none;
  font-weight: 600;
  transition: background 0.3s ease;
  display: inline-block;
}

  .btn-primary:hover {
    background: #00bcd4;
    color: #fff;
  }

/* ANIMATION */
@keyframes fadeInUp {
  from {
    transform: translateY(20px);
    opacity: 0;
  }

  to {
    transform: translateY(0);
    opacity: 1;
  }
}

/* ABOUT TRACKFIT */
.about-trackfit {
  background: #e3f2fd;
  padding: 50px 30px;
  text-align: center;
  border-radius: 15px;
  margin: 50px auto;
  max-width: 800px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.05);
}

  .about-trackfit h2 {
    font-size: 2.3rem;
    margin-bottom: 25px;
    color: #2c3e50;
  }

  .about-trackfit ul {
    list-style: none;
    padding: 0;
    text-align: left;
    max-width: 600px;
    margin: 0 auto;
  }

  .about-trackfit li {
    font-size: 1.1rem;
    margin-bottom: 15px;
    position: relative;
    padding-left: 25px;
  }

    .about-trackfit li::before {
      content: "✔";
      color: #00e5ff;
      position: absolute;
      left: 0;
      font-weight: bold;
    }

/* FITNESS FACTS & DID YOU KNOW */
.fitness-facts {
  background: #ffffff;
  margin: 60px auto;
  padding: 40px 30px;
  max-width: 1000px;
  border-radius: 15px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.05);
  text-align: center;
}

  .fitness-facts h2 {
    font-size: 2.3rem;
    margin-bottom: 30px;
    color: #2c3e50;
  }

.facts-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 30px;
  justify-content: center;
}

.fact-card {
  background: #f0f4f8;
  color: #333;
  padding: 25px;
  border-radius: 15px;
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.05);
  flex: 1 1 280px;
  transition: transform 0.3s ease;
}

  .fact-card:hover {
    transform: translateY(-6px);
  }

  .fact-card h3 {
    font-size: 1.4rem;
    margin-bottom: 10px;
    color: #007bff;
  }

  .fact-card p {
    font-size: 1rem;
    line-height: 1.5;
  }

/* WORKOUT TIPS */
.workout-tips {
  max-width: 900px;
  background: #e3f2fd;
  color: #2c3e50;
  padding: 50px 30px;
  margin: 60px auto;
  border-radius: 15px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.05);
}

  .workout-tips h2 {
    text-align: center;
    font-size: 2.4rem;
    margin-bottom: 30px;
  }

  .workout-tips ul {
    list-style: none;
    padding: 0;
    font-size: 1.1rem;
    line-height: 1.8;
    max-width: 600px;
    margin: 0 auto;
  }

  .workout-tips li {
    display: flex;
    align-items: center;
    margin-bottom: 15px;
  }

    .workout-tips li span {
      margin-right: 12px;
      font-size: 1.4rem;
    }

/* FOOTER */
.footer {
  background-color: #1e1e2f;
  color: white;
  text-align: center;
  padding: 15px 0;
  font-size: 14px;
}

  .footer a {
    color: #00e5ff;
    text-decoration: none;
    margin: 0 8px;
  }

    .footer a:hover {
      text-decoration: underline;
    }





<header class="header">
  <a href="/" class="logo">TrackFit</a>

  <div class="header-icons">
    <!-- Bell icon linking to remainders -->
    <a href="/remainders" class="notification-icon" title="Notifications">
      <i class="fas fa-bell"></i>
    </a>

    <!-- Profile icon -->
    <a href="/profile" class="profile-icon">
      <img src="/assets/images/user-icon.png" alt="Profile" />
    </a>
  </div>
</header>



<section class="hero-section">
  <div class="hero-content">
    <h1>Welcome to TrackFit</h1>
    <p>Your journey to a healthier lifestyle starts here. Discover workouts, track your progress, and stay motivated.</p>
    <a routerLink="/user-dashboard" class="btn-primary">Explore Now</a>
  </div>
</section>

<section class="about-trackfit">
  <h2>About TrackFit</h2>
  <ul>
    <li>Personalized fitness tracking</li>
    <li>Goal setting and progress monitoring</li>
    <li>Expert-recommended workouts</li>
    <li>Motivational tips and daily reminders</li>
  </ul>
</section>

<section class="fitness-facts">
  <h2>Fitness Facts</h2>
  <div class="facts-grid">
    <div class="fact-card">Exercise improves mental health and mood.</div>
    <div class="fact-card">30 minutes a day can make a big difference.</div>
    <div class="fact-card">Staying hydrated boosts energy levels.</div>
  </div>
</section>

<section class="fitness-facts">
  <h2>Did You Know?</h2>
  <div class="facts-grid">
    <div class="fact-card">
      <h3>30 Minutes</h3>
      <p>of moderate exercise daily can boost your mood and energy.</p>
    </div>
    <div class="fact-card">
      <h3>Regular Workouts</h3>
      <p>help improve your heart health and reduce risk of chronic diseases.</p>
    </div>
    <div class="fact-card">
      <h3>Consistency</h3>
      <p>is the key to long-term fitness success. Start small, stay committed!</p>
    </div>
  </div>
</section>

<section class="workout-tips">
  <h2>Pro Tips for Your Workouts</h2>
  <ul>
    <li><span>💧</span> Stay hydrated before, during, and after exercise.</li>
    <li><span>🧘‍♂️</span> Warm up properly to avoid injuries.</li>
    <li><span>🍎</span> Fuel your body with nutritious meals.</li>
    <li><span>😴</span> Get enough rest for better recovery.</li>
  </ul>
</section>

<footer class="footer">
  <p>&copy; 2025 TrackFit | <a href="#">Contact Us</a> | <a href="#">Privacy Policy</a></p>
</footer>t
