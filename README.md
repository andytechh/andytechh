- 👋 Hi, I’m Andy G. Lazarte 2nd year BSIT Student
- 👀 I’m interested in backend development
- 🌱 I’m currently learning c++ and java
- 💞️ I’m looking to collaborate on any projects in c++
- 📫 How to reach me? dm me on my fb account https://www.facebook.com/profile.php?id=100031935578704
- Portfolio -[ https://main--whimsical-cassata-73e697.netlify.app/](https://myportfolio-andy.netlify.app/)

<!---
andytechh/andytechh is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
https://www.figma.com/design/lGuqUQJdSZvV0tNcmmfya4/Untitled?node-id=1-2&t=UjovqP2ujPcfGQUB-1
--->
https://elms.catcollege.edu.ph/login/index.php
#include <iostream>

using namespace std;

// Function to find waiting time for each process
void findWaitingTime(int processes[], int n, int bt[], int wt[]) {
    wt[0] = 0; // First process has no waiting time

    // Calculating waiting time for each process
    for (int i = 1; i < n; i++) {
        wt[i] = bt[i - 1] + wt[i - 1];
    }
}

// Function to calculate turnaround time
void findTurnAroundTime(int processes[], int n, int bt[], int wt[], int tat[]) {
    for (int i = 0; i < n; i++) {
        tat[i] = bt[i] + wt[i];
    }
}

// Function to calculate average waiting and turnaround time
void findAverageTime(int processes[], int n, int bt[]) {
    int wt[n], tat[n];
    float total_wt = 0, total_tat = 0;

    // Calculate waiting time
    findWaitingTime(processes, n, bt, wt);

    // Calculate turnaround time
    findTurnAroundTime(processes, n, bt, wt, tat);

    // Display process details
    cout << "Processes  Burst Time  Waiting Time  Turnaround Time\n";
    for (int i = 0; i < n; i++) {
        total_wt += wt[i];
        total_tat += tat[i];
        cout << "   " << processes[i] << "\t\t" << bt[i] << "\t    " << wt[i] << "\t\t   " << tat[i] << endl;
    }

    // Display average waiting and turnaround time
    cout << "\nAverage Waiting Time: " << (total_wt / n) << endl;
    cout << "Average Turnaround Time: " << (total_tat / n) << endl;
}

int main() {
    int n;

    // Input number of processes
    cout << "Enter number of processes: ";
    cin >> n;

    int processes[n], burst_time[n];

    // Input process IDs and burst times
    cout << "Enter burst time for each process:\n";
    for (int i = 0; i < n; i++) {
        processes[i] = i + 1;
        cout << "Process " << i + 1 << ": ";
        cin >> burst_time[i];
    }

    // Calculate and display scheduling details
    findAverageTime(processes, n, burst_time);

    return 0;
}
