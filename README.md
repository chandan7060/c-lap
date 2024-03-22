#include <iostream>

int main() {
    int count = 0;
    int num;

    while (true) {
        std::cout << "Enter a number: ";
        std::cin >> num;

        if (!std::cin) {
            std::cout << "Invalid input. Please enter a valid number." << std::endl;
            std::cin.clear();
            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
            continue;
        }

        if (num % 8 == 0) {
            count++;
            std::cout << "Valid number. Count: " << count << std::endl;
        } else {
            std::cout << "Invalid number. Please enter a valid number." << std::endl;
        }

        std::cout << "Do you want to continue? (y/n): ";
        char choice;
        std::cin >> choice;

        if (choice != 'y' && choice != 'Y') {
            break;
        }
    }

    return 0;
}
