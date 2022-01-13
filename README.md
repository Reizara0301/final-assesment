# final-assesment
#include <iostream>
#include <string>
#include <array>
#include <math.h>
#include <algorithm>
using namespace std;

static void askSugar() {
	// The user want to add sugar or not.
	char userInput;
	cout << "Do you want your drink with sugar? If YES press 'Y' and if NO press 'N':" << endl;
	cin >> userInput;
	userInput = toupper(userInput);

	switch (userInput) {
	case 'Y':
		cout << "Alright then" << endl;
		break;
	case 'N':
		cout << "NO sugar" << endl;
		break;
	default:
		cout << "Invalid input" << endl;
	}
}

static void payment(int itemPrice) {
	int userMoney;
	cout << "Enter your money: ";
	cin >> userMoney;
	
	if (userMoney > itemPrice) {
		cout << "Purchase successful!" << endl;
		cout << "Heres your change: " << userMoney - itemPrice << endl;
		cout << "Have a nice day!" << endl;
	}
	else if (userMoney < itemPrice) {
		cout << "Not enough money!" << endl;
		cout << "Come back again if you have enough money" << endl;
	}
}


int main()
{
	int choose{};
	string menu[4][4] = {
		{"Coffee\t", "Price(aed)\t", "Tea\t", "Price(aed)\t"},
		{"Ice Coffee\t", "3 aed\t", "Ice tea\t", "3 aed\t"},
		{"Milk Coffee\t", "2 aed\t", "Milk tea\t", "2 aed\t"},
		{"Black Coffee\t", "1 aed\t", "Black tea\t", "1 aed\t"},
	};

	for (int i = 0; i < 4; i++) {
		for (int j = 0; j < 4; j++) {
			cout << menu[i][j] << " ";
		}
		cout << endl;
	}

	char drink; //use the if-else statements for waht the user wants to drink.
	cout << "what do you want? Choose to press '1' for coffee or '2' for tea? " << endl;
	cin >> drink;

	if (drink == '1') {
		cout << "Choose what kind coffee do you prefer? " << endl;
		cout << "A. Iced coffee" << endl;
		cout << "B. Milk coffee" << endl;
		cout << "C. Black coffee" << endl;
		char coffeeSelection;
		cin >> coffeeSelection;
		coffeeSelection = toupper(coffeeSelection);

		//After the user decide that drinks of their choice, use switch to show the price.
		switch (coffeeSelection) {
		case 'A': {
			cout << "total amount will be 3aed" << endl;
			askSugar();
			int itemCost = 3;
			payment(itemCost);
		}
			break;

		case 'B': {
			cout << "total amount will be 2aed" << endl;
			askSugar();
			int itemCost = 2;
			payment(itemCost);
		}
			break;

		case 'C': {
			cout << "total amount will be 1aed" << endl;
			askSugar();
			int itemCost = 1;
			payment(itemCost);
		}
			break;

		default:
			cout << "Invalid input." << endl;
			break;
		}

	}
	else if (drink == '2') {
		cout << "Choose what kind of tea do you prefer?" << endl;
		cout << "A. Ice tea" << endl;
		cout << "B. Milk tea" << endl;
		cout << "C. Black tea" << endl;
		char teaSelection;
		cin >> teaSelection;
		teaSelection = toupper(teaSelection);

		//After the user decide that drinks of their choice, use switch to show the price.
		switch (teaSelection) {
		case 'A': {
			cout << "total amount will be 3aed" << endl;
			askSugar();
			int itemCost = 3;
			payment(itemCost);
		}
			break;

		case 'B': {
			cout << "total amount will be 2aed" << endl;
			askSugar();
			int itemCost = 2;
			payment(itemCost);
		}
			break;

		case 'C': {
			cout << "total amount will be 1aed" << endl;
			askSugar();
			int itemCost = 1;
			payment(itemCost);
		}
			break;

		default:
			cout << "Invalid input." << endl;
			break;
		}
	}
	else {
		cout << "Invalid input " << endl;
	}
}
