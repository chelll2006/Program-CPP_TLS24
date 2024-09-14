#include <iostream>
#include <iomanip>
using namespace std;

// Function to calculate calories burned
double CalculateCalories(double weight, double duration, double met) {
    return duration * met * weight;
}

int main() {
    double weight, duration, speed;
    double met;

    // user input
    cout << "Enter your weight in kg: ";
    cin >> weight;
    cout << "Enter the duration of the walk in hours: ";
    cin >> duration;
    cout << "Enter the walking speed in mph: ";
    cin >> speed;

    // determine MET value based on walking speed
    if (speed < 3.0) {
        met = 2.5; // Light walking
    } else if (speed < 4.0) {
        met = 3.0; // Moderate walking
    } else if (speed < 5.0) {
        met = 3.8; // Brisk walking
    } else {
        met = 4.5; // Fast walking
    }

    //calculate the calories spent
    double calories = CalculateCalories(weight, duration, met); 

    // Output the result
    cout << "Calories burned: " << calories << " kcal" << endl;
    cout << "Congratulation for the calories burn, keep going!!" << endl;

    return 0;
}
