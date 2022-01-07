# Practice

    #include <iostream>
    #include <string>
    using namespace std;

    string ageFunction(int age) {

        string answer;

        if (age >= 16 && age <= 21) {
            cout << "\nDo you want to go to the mall? (Y for Yes, N for No): ";
            cin >> answer;
            while (answer.length() != 1) {
                cout << "\nInvalid input. (Y for Yes, N for No)" << endl;
                cin >> answer;
            }
        }
        else if (age >= 22 && age < 30) {
            cout << "\nDo you want to go on a trip to Hawaii? (Y for Yes, N for No): ";
            cin >> answer;
            while (answer.length() != 1) {
                cout << "\nInvalid input. (Y for Yes, N for No)" << endl;
                cin >> answer;
            }
        }
        else {
            cout << "\nSorry, your age is not eligible.\nAge must be 16-30." << endl;
        }
        return answer;
    }

    void response(string input) {

        if ((input == "y" || input == "Y")) {
            cout << "\nEnjoy the trip!" << endl;
        }
        else if ((input == "n" || input == "N")) {
            cout << "\nYour trip is cancelled." << endl;
        }
        else
        {
            cout << "\nInvalid input." << endl;
        }
    }

    int main()
    {
        int age{};
        string answer{};

        cout << "Enter your age: ";
        cin >> age;
        while (cin.fail())
        {
            cin.clear();
            cin.ignore(1000, '\n');
            cout << "\nInvalid input. Enter a number again: ";
            cin >> age;
        }

        answer = ageFunction(age);
        response(answer);
    }
