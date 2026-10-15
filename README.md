#include <iostream>
#include <string>
#include <cstdlib>
#include <ctime>
using namespace std;

int main() {
    string msg;
    int choice, a, b, answer;

    srand(time(0));

    cout << "=============================\n";
    cout << "   FUN CHATBOT IN C++\n";
    cout << "=============================\n";
    cout << "Bot: Hello! Welcome to my chatbot.\n";
    cout << "Bot: Type 'bye' to exit.\n";

    while (true) {
        cout << "\nYou: ";
        getline(cin, msg);

        if (msg == "bye" || msg == "Bye") {
            cout << "Bot: Goodbye! See you again!\n";
            break;
        }
        else if (msg == "hello" || msg == "hi" ||
                 msg == "Hello" || msg == "Hi") {
            cout << "Bot: Hello! Nice to meet you!\n";
        }
        else if (msg == "name") {
            cout << "Bot: My name is FunBot!\n";
        }
        else if (msg == "how are you") {
            cout << "Bot: I am great! Thanks for asking.\n";
        }
        else if (msg == "joke") {
            cout << "Bot: Why do programmers love C++?\n";
            cout << "Bot: Because they enjoy class!\n";
        }
        else if (msg == "study") {
            cout << "Bot: Study for 25 minutes, then take "
                 << "a 5-minute break!\n";
        }
        else if (msg == "motivate") {
            cout << "Bot: Believe in yourself. Keep learning!\n";
        }
        else if (msg == "game") {
            int secret = rand() % 10 + 1;
            int guess;

            cout << "Bot: Guess a number between 1 and 10!\n";

            do {
                cout << "Your guess: ";

                if (!(cin >> guess)) {
                    cin.clear();
                    cin.ignore(10000, '\n');
                    cout << "Bot: Please enter a number.\n";
                    continue;
                }

                if (guess < secret)
                    cout << "Bot: Too low! Try again.\n";
                else if (guess > secret)
                    cout << "Bot: Too high! Try again.\n";
                else
                    cout << "Bot: Correct! You win!\n";

            } while (guess != secret);

            cin.ignore(10000, '\n');
        }
        else if (msg == "calculator") {
            cout << "Enter two numbers: ";

            if (!(cin >> a >> b)) {
                cin.clear();
                cin.ignore(10000, '\n');
                cout << "Bot: Invalid numbers.\n";
                continue;
            }

            cout << "1. Addition\n";
            cout << "2. Subtraction\n";
            cout << "3. Multiplication\n";
            cout << "4. Division\n";
            cout << "Choose: ";

            if (!(cin >> choice)) {
                cin.clear();
                cin.ignore(10000, '\n');
                cout << "Bot: Invalid choice.\n";
                continue;
            }

            switch (choice) {
                case 1:
                    cout << "Result: " << a + b << "\n";
                    break;
                case 2:
                    cout << "Result: " << a - b << "\n";
                    break;
                case 3:
                    cout << "Result: " << a * b << "\n";
                    break;
                case 4:
                    if (b != 0)
                        cout << "Result: "
                             << (double)a / b << "\n";
                    else
                        cout << "Bot: Cannot divide by zero!\n";
                    break;
                default:
                    cout << "Bot: Invalid choice!\n";
            }

            cin.ignore(10000, '\n');
        }
        else if (msg == "help") {
            cout << "\nBot: Here are my activities:\n";
            cout << "- hello : Greeting\n";
            cout << "- name : My name\n";
            cout << "- joke : Tell a joke\n";
            cout << "- study : Study advice\n";
            cout << "- motivate : Motivation\n";
            cout << "- game : Play number guessing\n";
            cout << "- calculator : Calculate numbers\n";
            cout << "- bye : Exit chatbot\n";
        }
        else {
            cout << "Bot: I don't understand. Type 'help' "
                 << "to see my activities.\n";
        }
    }

    return 0;
}