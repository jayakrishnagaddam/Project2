import { Component } from '@angular/core';

interface Workout {
  name: string;
  category: string;
  duration: string;
  image: string;
  instructions: string[];
}

@Component({
  selector: 'app-user-dashboard',
  templateUrl: './user-dashboard.component.html',
  styleUrls: ['./user-dashboard.component.css']
})
export class UserDashboardComponent {
  searchQuery: string = '';
  selectedCategory: string = 'All';
  selectedWorkout: Workout | null = null;

  categories: string[] = ['All', 'Cardio', 'Strength', 'Flexibility', 'Endurance'];

  workouts: Workout[] = [
    {
      name: 'Push Ups',
      category: 'Strength',
      duration: '15 mins',
      image: 'assets/images/pushups.jpg',
      instructions: [
        'Place your hands shoulder-width apart.',
        'Keep your body straight.',
        'Lower yourself until your chest nearly touches the floor.',
        'Push back up to the starting position.',
      ]
    },
    {
      name: 'Running',
      category: 'Cardio',
      duration: '30 mins',
      image: 'assets/images/running.jpg',
      instructions: [
        'Warm up with a light jog.',
        'Maintain a steady pace.',
        'Cool down by walking.',
      ]
    },
    {
      name: 'Yoga',
      category: 'Flexibility',
      duration: '20 mins',
      image: 'assets/images/yoga.jpg',
      instructions: [
        'Start with deep breathing.',
        'Perform basic yoga poses.',
        'Focus on stretching and flexibility.',
      ]
    },
    {
      name: 'Cycling',
      category: 'Cardio',
      duration: '45 mins',
      image: 'assets/images/cycling.jpg',
      instructions: [
        'Adjust your bike seat for comfort.',
        'Maintain a steady pace.',
        'Wear a helmet for safety.',
      ]
    },
    {
      name: 'Plank',
      category: 'Endurance',
      duration: '5 mins',
      image: 'assets/images/plank.jpg',
      instructions: [
        'Keep your forearms on the ground.',
        'Maintain a straight line from head to heels.',
        'Hold the position as long as possible.',
      ]
    },
    {
      name: 'Squats',
      category: 'Strength',
      duration: '20 mins',
      image: 'assets/images/squats.jpg',
      instructions: [
        'Stand with feet shoulder-width apart.',
        'Lower your body as if sitting on a chair.',
        'Keep your back straight.',
        'Return to starting position.',
      ]
    },
    {
      name: 'Jump Rope',
      category: 'Cardio',
      duration: '10 mins',
      image: 'assets/images/jumprope.jpg',
      instructions: [
        'Hold handles firmly.',
        'Jump with both feet together.',
        'Maintain a steady rhythm.',
      ]
    }
  ];

  get filteredWorkouts(): Workout[] {
    return this.workouts.filter(workout =>
      (this.selectedCategory === 'All' || workout.category === this.selectedCategory) &&
      workout.name.toLowerCase().includes(this.searchQuery.toLowerCase())
    );
  }

  setCategory(category: string) {
    this.selectedCategory = category;
    this.selectedWorkout = null; // Close instructions on category change
  }

  onCardClick(workout: Workout) {
    if (this.selectedWorkout === workout) {
      this.selectedWorkout = null; // Collapse if same card clicked
    } else {
      this.selectedWorkout = workout; // Expand clicked card
    }
  }
}
