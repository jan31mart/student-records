#include <iostream>
using namespace std;
#include <string>


string calculatescore(int score) {
    
    if (score >= 90 && score <= 100){
        return "A";
          
    } else if ( score >= 80 && score <= 89) {
        
        return "B";
        
    } else if (score >= 70 && score <= 79) {
        return "C";
        
    } else if (score >= 60 && score <= 69) {
        return "D";
        
    } else {
   
    return "F";
    
}
}

int main() {
 
int numberstud;
//double sum = 0;

cout << "Enter number of students: " << endl;
    cin >> numberstud; 

string studentname[numberstud];
int numbertest[numberstud];
double testscore[numberstud][5];
double average[numberstud];
string grades[numberstud];


void displayResults(string studentname[], double average[], double grades[], int numberstud);
double calculateAverage(int scores[], int numScores);
char determineGrade(double avgScore); 
    
for(int i = 0; i < numberstud; i++){
cout << "Enter name of student " << (i + 1) << ":" << endl;
cin >> studentname[i];

double sum = 0;

cout << "Enter number of test scores: ";
cin >>  numbertest[i];



for (int j = 0; j < numbertest[i]; j++) {
cout << "Enter score " << (j + 1) << ":";
cin >> testscore [i][j];
sum += testscore[i][j];
}

average[i] = sum / numbertest[i];

grades[i] = calculatescore(average[i]);
}

cout << "Result:" << endl;
cout << "--------------------------------" << endl; 
cout << left  << "Student" << " | "  << "Average" << " | " << "Grade" << endl; 
cout << "--------------------------------" << endl; 
for (int i = 0; i < numberstud; i++) { 
cout << left  << studentname[i] << " | " << average[i] << " | " << grades[i] << endl; 
} 
cout << "--------------------------------" << endl; 

return 0;
}


