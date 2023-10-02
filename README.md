- 👋 Hi, I’m Andy G. Lazarte 1st year BSIT Student
- 👀 I’m interested in backend development
- 🌱 I’m currently learning c++ and java
- 💞️ I’m looking to collaborate on any projects in c++
- 📫 How to reach me? dm me on my fb account https://www.facebook.com/profile.php?id=100031935578704

<!---
andytechh/andytechh is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
# libarary_management_system-

//task5
int hours_work;
int income;
float deduction;
int netincome;

cout << "Enter the Hours of work: ";
cin >> hours_work;

income = hours_work*750.00;
deduction = income*(10.0/100.0);
netincome = income - static_cast<int>(deduction);

cout << "Income: " << income << endl;
cout << "Deduction: " << deduction << endl;
cout << "Net Income: " << netincome << endl;
//task6
int pants;
int shirts;
int totalAmount;

cout << "Enter the number of pants: ";
cin >> pants;
cout << "Enter the number of shirts: ";
cin >> shirts;

totalAmount = (pants*700.00) + (shirts*315.00);

cout << "Total amount to pay: " << totalAmount << endl;

// task7
int inches;
int foot;

cout << "Enter number of inches: ";
cin >> inches;
foot = inches / 12;

cout << inches << "is equivalent to: " << foot;

// task8
int base;
int height;
int AreaofTriangle;

cout << "Enter the base value: ";
cin >> base;
cout << "Enter the height: ";
cin >> height;

AreaofTriangle = (base * height)/2;
cout << "The area of a triangle: " << AreaofTriangle << endl;
