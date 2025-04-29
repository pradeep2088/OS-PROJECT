# Intelligent CPU Scheduler

[![GitHub License](https://img.shields.io/github/license/asish-1611/Intelligent_CPU_Schedular)](https://github.com/asish-1611/Intelligent_CPU_Schedular/blob/main/LICENSE)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)

A modern web-based visualization tool for understanding CPU scheduling algorithms through interactive simulations.

## Features

### Home Page
- Immersive video background with dynamic overlay
- Modern glassmorphism navigation bar
- Responsive design with smooth animations
- Quick access to core functionalities

### Algorithms Page
- Detailed explanations of scheduling algorithms
- Interactive accordion sections for:
  - Preemptive Scheduling (RR, SRTF, Priority)
  - Non-Preemptive Scheduling (FCFS, SJF, Priority)
- Visual flowchart of algorithm types
- Advantages/Disadvantages comparison
- Direct access to simulations

### Simulation Page
- interactive scheduling algorithm visualizations:
  1. First Come First Serve (FCFS)
  2. Shortest Job First (SJF)
  3. Shortest Remaining Time First (SRTF)
  4. Round Robin (RR)
  5. Priority (Preemptive)
  6. Priority (Non-Preemptive)
- Responsive grid layout with animated cards
- Individual simulation launch points
- Modern hover effects and transitions

### Algorithms Pages(in Algorithms Folder) (Interactive Features)
#### Common Features Across All Algorithms:
1. *Process Table Generation*
   - Customizable number of processes (1-10)
   - Random burst time generation
   - Editable arrival times
   - Priority input (for Priority algorithms)

2. *Calculation Engine*
   - Computes scheduling steps
   - Determines completion times
   - Calculates waiting and turnaround times

3. *Visualization Controls*
   - Play/Pause simulation
   - Step forward/Step backward
   - Reset simulation
   - Speed control (0.5x-2x)

4. *Dynamic Displays*
   - *Gantt Chart*:
     - Color-coded process blocks
     - Time markers for each segment
     - Idle periods visualization
   - *Ready Queue*:
     - Real-time updates
     - Visual indication of process states
     - Animated transitions

5. *Performance Metrics*
   - Individual process metrics:
     - Completion Time
     - Waiting Time
     - Turnaround Time
   - System averages:
     - Average Waiting Time
     - Average Turnaround Time

#### Algorithm-Specific Implementations:

1. *First Come First Serve (FCFS)*
   - Non-preemptive scheduling
   - Processes executed in arrival order
   - Visualizes convoy effect

2. *Shortest Job First (SJF)*
   - Non-preemptive version
   - Always selects shortest available job
   - Shows optimal waiting time

3. *Shortest Remaining Time First (SRTF)*
   - Preemptive version of SJF
   - Dynamic priority based on remaining time
   - Visualizes frequent context switches

4. *Round Robin (RR)*
   - Time quantum-based scheduling
   - Configurable quantum size
   - Circular queue visualization

5. *Priority Scheduling*
   - Both preemptive and non-preemptive versions
   - Priority-based selection
   - Visualizes priority inversion

## Technologies Used
- *Frontend*: HTML5, CSS3, JavaScript (Vanilla)
- *Styling*: 
  - CSS Grid/Flexbox layouts
  - Glassmorphism effects
  - Advanced animations and transitions
- *Fonts*: Google Fonts (Poppins, Inknut Antiqua)
- *Visualization*: Custom Gantt chart and queue implementations

## Getting Started

### Prerequisites
- Modern web browser (Chrome, Firefox, Edge recommended)
- Web server for local deployment (optional)

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/pradeep2088/OS-PROJECT.git
