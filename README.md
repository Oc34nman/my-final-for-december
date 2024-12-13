# my-final-for-december

#include<iostream>
using namespace std;
//function declaration
void Mutant();
void Rapidman();
void GordonRamsey();
void sigmawolf();
void skibiditoilet();
string items[5];
int playerhealth = 10000;
string inventory[10];
int money = 100;
void elotero();
void welmart_canada_editon();
//globalvariables:can be seen and used by all functions in the program


int main() {
	int score1[6];
	int room = 1;
	string choice;

	cout << "Welcome to colorful colorado!" << endl;
	while(choice != "quit" && playerhealth>0) {
		if (choice == "inventory") {
			for (int i = 0; i < 10; i++)
				cout << inventory[i] << " | ";
			cout << endl;
		}
		switch (room) {
		case 1:
			cout << "You are in a Raising canes,eating some food right before seeing on the TV  if you get all brainrot artifacts around colorado you can get a free wish,so you get out of your seat set for a journey  . You can go (e)ast." << endl;
			cin >> choice;
			if (choice == "east")
				room = 2;
			else if (choice !="inventory")
				cout << " I dont understand that." << endl;
			break;
		case 2:
			cout << "You are in a abandoned chuck e cheese,theres a chance you could get attacked by a mutant minions that has low health but can damage alot,you can go (e)ast or (s)outh." << endl;
			Mutant();
			cin >> choice;
			if (choice == "east")
				room = 3;
			else if (choice == "south")
				room = 3;
			else if (choice != "inventory")
				cout << "I dont understand." << endl;
			break;
		case 3:
			cout << "Your at commerce city,there will be a artifact but first youll have to defeat The rapid man the ugly corrupt mascot of the coloardo rapids.Hes blocked the exits you need to defeat him to pass.He does low damage but has high health.You can go (s)outh and (w)est" << endl;
			Rapidman();
			cin >> choice;
			if (choice == "west")
				room = 2;
			else if (choice == "south")
				room = 4;
			else
				cout << "I dont understand." << endl;
			break;
		case 4:
			cout << "Your at the denver airport very wierd and eery maybe just decoration? You can go (s)outh, (w)est ,(n)orth and (e)ast " << endl;
			cin >> choice;
			if (choice == "west")
				room = 5;
			else if (choice == "south")
				room = 7;
			else if (choice == "east")
				room = 6;
			else if (choice == "north")
				room = 3;
			else if (choice != "inventory")
				cout << "I dont understand." << endl;
			break;
		case 5:
			cout << "Your at the mountains very chilly try to stay warm , You can go (e)ast " << endl;
			cin >> choice;
			if (choice == "east")
				room = 4;
			break;
		case 6:
			welmart_canada_editon();
			cout << "Ey went to faer and now yous in canada have some good stuff , You can go (e)ast " << endl;
			cin >> choice;
			if (choice == "east")
				room = 4;
			break;
		case 7:
			cout << "Your in Denver heart of colorado but the ultra sigma wolf has escaped prison and has one of the artifacts try to contain it, you can go (s)outh and (w)est. " << endl;
			sigmawolf();
			cin >> choice;
			if (choice == "south")
				room = 8;
			else if (choice == "west")
				room = 9;
			break;
		case 9:
			cout << "Your in colorado springs,you find out the last artifact has been taken to manchester go west to get on a plane and take back the artifact and unlock your wish, you need to go (w)est or  go (e)ast if your not ready " << endl;
			elotero();
			cin >> choice;
			if (choice == "east")
				room = 7;
			else if (choice == "west")
				room = 10;
			break;
		case 10:
			cout << "Your in Manchester,Turns out its Gordon ramsey and  says he knows places in manchester to destory the artifact get it before he causes devestation to the world. " << endl;
			GordonRamsey();
			cin >> choice;
			if (choice == "east")
				room = 9;

			break;
		case 8:
			cout << "You made it to the tomb of dawkins, as you breath before you wish,you dont just hear but feel aura  as something skibdi dop dop yes yes skibidi dip dip comes out of the ground and takes your artifacts.Go get therm back and make the wish before it tears the universe apart." << endl;
			if (inventory[6] == "key") {
				cout << "the final boss appears" << endl;
				skibiditoilet();
				if (playerhealth > 0) {
					cout << "you won" << endl;
				}
				else {
					cout << "you died" << endl;
				}

			}
			else {
				cout << "go find the key" << endl;
				cin >> choice;
				if (choice == "west")
					room = 7;
			}



			break;

		}
	}//end of game loop
	
}//end of main

void elotero() {
	char input = 'o';

	cout << endl << endl << "----------------------" << endl;
	cout << "shop" << endl;
	while (input != 'q') {
		cout << "press c for coca cola($10), l for elote($20), b for a basketball on fire shirt($20), q to quit" << endl;
		cin >> input;
		switch (input) {
		case 'c':
			if (money >= 10) {

				cout << "you got coca cola!" << endl;
				inventory[0] = "coke";
				money -= 10;
			}
			else
				cout << "your broke!" << endl;
			break;
		case 'l':
			cout << "you got a elote!" << endl;
			inventory[1] = "elote";
			break;
		case 'b':
			cout << "you got a basket ball on fire shirt!" << endl;
			inventory[2] = "basket ball on fire shirt";
			money -= 50;
		default:

			cout << "youre broke" << endl;
			break;

		}
	}
}

void welmart_canada_editon() {
	char input = 'o';

	
	while (input != 'q') {
		cout << endl << endl << "----------------------" << endl;
		cout << "shop" << endl;
		cout << "press m for maple syrup[($10), i for igloo thrower($20), a for alphonso davies jersey($50), q to quit" << endl;
		cin >> input;
		switch (input) {
		case 'm':
			if (money >= 10) {

				cout << "you got maple syrup!" << endl;
				inventory[5] = "maple syrup";
				money -= 10;
			}
			else
				cout << "your broke!" << endl;
			break;
		case 'i':
			cout << "you got the igloo thrower!" << endl;
			inventory[3] = "igloo thrower";
			break;
		case 'a':
			cout << "you got a alphonso davies jersey!" << endl;
			inventory[4] = "alphonso davies jersey";
			money -= 50;
		default:

			cout << "youre broke" << endl;
			break;

		}
	}
}


void Mutant() {
	int monsterhealth = 20;
	int input;
	int num;
	cout << endl << endl << "------------GO GET THERM------------" << endl;
	while (playerhealth > 0 && monsterhealth > 0) {

		//monster attack
		if (items[1] == "basketball on fire shirt") {
			num = rand() % 7 + 3;
			cout << "your shirt  abords the blow and you get hit for {" << num << " damge!" << endl;

			playerhealth -= num;
		}
		
		else if (items[1] == "alphonso davies jersey") {
			num = rand() % 7 + 3;
			cout << "your jersey  abords the blow and you get hit for {" << num << " damge!" << endl;

			playerhealth -= num;
		}
		
		else {
			num = rand() % 2 + 3;
			cout << "the mutant  bites your bare arm for " << num << "dmg" << endl;
			playerhealth -= num;


			cout << "the mutant bites you for 4 dmg" << endl;
			playerhealth -= 4;

			//get players choice:
			cout << "press 1 to attack, 2 to drink health tonic, 3 to try to escape!" << endl;
			cin >> input;

			switch (input) {
			case 1:
				//player attack
				if (items[0] == "elote") {
					num = rand() % 10 + 10; // range from 10-20
					cout << "you slash the mutant with your weapon for " << num << " damge!" << endl;
					monsterhealth -= num;
				}
				else {
					num = rand() % 5 + 2; //range from 2-7
					cout << "you punch the mutant with your sword for" << num << "dmg" << endl;
					monsterhealth -= num;

					cout << "you hit the mutant for 10 dmg" << endl;
					monsterhealth -= 10;
				}
				break;
			case 2: // health potion
				if (items[3] == "coca cola") {
					cout << "glug glug !" << endl;
					playerhealth += 50;
					items[3] = " "; //erase the potion

				}
				else cout << " sorry, you dont have any tonics." << endl;

				break;
			case 3: // escape
				num = rand() & 100;
				if (num > 75) {//25% chance of escaping
					cout << "you successfully run away!" << endl;
					monsterhealth = 0;
				}
			
				

				break;

			case 4: // health potion
				if (items[4] == "maple syrup") {
					cout << "glug glug !" << endl;
					playerhealth += 50;
					items[4] = " "; //erase the potion

				}
				else cout << " sorry, you dont have any tonics." << endl;

				break;

			case 5:
				//player attack
				if (items[0] == "igloo thrower") {
					num = rand() % 10 + 10; // range from 10-20
					cout << "you throw a igloo at the mutant with your weapon for " << num << " damge!" << endl;
					monsterhealth -= num;
				}
				else {
					num = rand() % 5 + 2; //range from 2-7
					cout << "you punch the mutant with your igloos for" << num << "dmg" << endl;
					monsterhealth -= num;

					cout << "you hit the mutant for 25 dmg" << endl;
					monsterhealth -= 10;
				}
				break;

			default:
				cout << "sorry not an option" << endl;






				cout << "you hit the mutant for 10 dmg" << endl;
				monsterhealth -= 10;

				cout << "your health:" << playerhealth << endl;
				cout << "mutant health:" << monsterhealth << endl;



			}
			if (monsterhealth < 0)
				cout << "---------------------------end of battle---------------------------" << endl;
		}
	}
}

void Rapidman() {
	int monsterhealth = 30;
	int input;
	int num;
	cout << endl << endl << "------------GO GET THERM------------" << endl;
	while (playerhealth > 0 && monsterhealth > 0) {
		
		//monster attack
		if (items[1] == "basketball on fire shirt") {
			num = rand() % 7 + 3;
			cout << "your shirt  abords the blow and you get hit for {" << num << " damge!" << endl;

			playerhealth -= num;
		}

		else if (items[1] == "alphonso davies jersey") {
			num = rand() % 7 + 3;
			cout << "your jersey  abords the blow and you get hit for {" << num << " damge!" << endl;

			playerhealth -= num;
		}

		else {
			num = rand() % 5 + 3;
			cout << "the rapid man kicks your legs for" << num << "dmg" << endl;
			playerhealth -= num;


			cout << "the rapid man kicks you for 9 dmg" << endl;
			playerhealth -= 9;

			//get players choice:
			cout << "press 1 to attack, 2 to drink health tonic, 3 to try to escape!" << endl;
			cin >> input;

			switch (input) {
			case 1:
				//player attack
				if (items[0] == "elote") {
					num = rand() % 10 + 10; // range from 10-20
					cout << "you slash the rapidman with your weapon for " << num << " damge!" << endl;
					monsterhealth -= num;
				}
				else {
					num = rand() % 7 + 4; //range from 2-7
					cout << "you punch the rapidman with your sword for" << num << "dmg" << endl;
					monsterhealth -= num;

					cout << "you hit the rapid man for " << num << endl;
					monsterhealth -= 14;
				}
				break;
			case 2: // health potion
				if (items[3] == "coca cola") {
					cout << "glug glug !" << endl;
					playerhealth += 50;
					items[3] = " "; //erase the potion

				}
				else cout << " sorry, you dont have any tonics." << endl;

				break;
			case 3: // escape
				num = rand() & 100;
				if (num > 75) {//25% chance of escaping
					cout << "you successfully run away!" << endl;
					monsterhealth = 0;
				}



				break;

			case 4: // health potion
				if (items[4] == "maple syrup") {
					cout << "glug glug !" << endl;
					playerhealth += 50;
					items[4] = " "; //erase the potion

				}
				else cout << " sorry, you dont have any tonics." << endl;

				break;

			case 5:
				//player attack
				if (items[0] == "igloo thrower") {
					num = rand() % 10 + 10; // range from 10-20
					cout << "you throw a igloo at the rapid man with your weapon for " << num << " damge!" << endl;
					monsterhealth -= num;
				}
				else {
					num = rand() % 5 + 2; //range from 2-7
					cout << "you punch the rapid man with your igloos for" << num << "dmg" << endl;
					monsterhealth -= num;

					cout << "you hit the rapidman for 25 dmg" << endl;
					monsterhealth -= 10;
				}
				break;

			default:
				cout << "sorry not an option" << endl;



				



				cout << "you hit the rapid man for 10 dmg" << endl;
				monsterhealth -= 10;

				cout << "your health:" << playerhealth << endl;
				cout << "rapidman  health:" << monsterhealth << endl;



			}
			if (monsterhealth < 0)																		
				cout << "---------------------------end of battle---------------------------" << endl;
			if (playerhealth < 0)
				cout << "you died mane" << endl;
		}
	}
}

void GordonRamsey() {
	int monsterhealth = 26;
	int input;
	int num;
	cout << endl << endl << "------------GO GET THERM------------" << endl;
	while (playerhealth > 0 && monsterhealth > 0) {

		//monster attack
		if (items[1] == "basketball on fire shirt") {
			num = rand() % 7 + 3;
			cout << "your shirt  abords the blow and you get hit for {" << num << " damge!" << endl;

			playerhealth -= num;
		}

		else if (items[1] == "alphonso davies jersey") {
			num = rand() % 7 + 3;
			cout << "your jersey  abords the blow and you get hit for {" << num << " damge!" << endl;

			playerhealth -= num;
		}

		else {
			num = rand() % 15 + 12;
			cout << "Gordan ramsey burns your hands for" << num << "dmg" << endl;
			playerhealth -= num;


			cout << "Gordon ramsey burned you for 25 dmg" << endl;
			playerhealth -= 15;

			//get players choice:
			cout << "press 1 to attack, 2 to drink health tonic, 3 to try to escape!" << endl;
			cin >> input;

			switch (input) {
			case 1:
				//player attack
				if (items[0] == "elote") {
					num = rand() % 10 + 10; // range from 10-20
					cout << "you slash gordon ramsey with your weapon for " << num << " damge!" << endl;
					monsterhealth -= num;
				}
				else {
					num = rand() % 5 + 2; //range from 2-7
					cout << "you punch gordon ramsey with your sword for" << num << "dmg" << endl;
					monsterhealth -= num;

					cout << "you hit gordon ramsey for 17 dmg" << endl;
					monsterhealth -= 10;
				}
				break;
			case 2: // health potion
				if (items[3] == "coca cola") {
					cout << "glug glug !" << endl;
					playerhealth += 50;
					items[3] = " "; //erase the potion

				}
				else cout << " sorry, you dont have any tonics." << endl;

				break;
			case 3: // escape
				num = rand() & 100;
				if (num > 75) {//25% chance of escaping
					cout << "you successfully run away!" << endl;
					monsterhealth = 0;
				}



				break;

			case 4: // health potion
				if (items[4] == "maple syrup") {
					cout << "glug glug !" << endl;
					playerhealth += 50;
					items[4] = " "; //erase the potion

				}
				else cout << " sorry, you dont have any tonics." << endl;

				break;

			case 5:
				//player attack
				if (items[0] == "igloo thrower") {
					num = rand() % 10 + 10; // range from 10-20
					cout << "you throw a igloo at gordon ramsey with your weapon for " << num << " damge!" << endl;
					monsterhealth -= num;
				}
				else {
					num = rand() % 5 + 2; //range from 2-7
					cout << "you punch gordon ramsey with your igloos for" << num << "dmg" << endl;
					monsterhealth -= num;

					cout << "you hit gordon ramsey for 25 dmg" << endl;
					monsterhealth -= 10;
				}
				break;

			default:
				cout << "sorry not an option" << endl;






				cout << "you hit gordon ramsey for 10 dmg" << endl;
				monsterhealth -= 10;

				cout << "your health:" << playerhealth << endl;
				cout << "gordon ramsey  health:" << monsterhealth << endl;



			}
			if (monsterhealth < 0)
				cout << "---------------------------end of battle---------------------------" << endl;
		}	if (playerhealth < 0)
			cout << "you died mane" << endl;
	}
}


void sigmawolf() {
	int monsterhealth = 32;
	int input;
	int num;
	cout << endl << endl << "------------GO GET THERM------------" << endl;
	while (playerhealth > 0 && monsterhealth > 0) {

		//monster attack
		if (items[1] == "basketball on fire shirt") {
			num = rand() % 7 + 3;
			cout << "your shirt  abords the blow and you get hit for {" << num << " damge!" << endl;

			playerhealth -= num;
		}

		else if (items[1] == "alphonso davies jersey") {
			num = rand() % 7 + 3;
			cout << "your jersey  abords the blow and you get hit for {" << num << " damge!" << endl;

			playerhealth -= num;
		}

		else {
			num = rand() % 15 + 12;
			cout << "The sigma wolf uses mango phonk to damage you for" << num << "dmg" << endl;
			playerhealth -= num;


			cout << "The sigma wolf uses mango phonk to damage you for 25 dmg" << endl;
			playerhealth -= 15;

			//get players choice:
			cout << "press 1 to attack, 2 to drink health tonic, 3 to try to escape!" << endl;
			cin >> input;

			switch (input) {
			case 1:
				//player attack
				if (items[0] == "elote") {
					num = rand() % 10 + 10; // range from 10-20
					cout << "you slash The sigma wolf with your weapon for " << num << " damge!" << endl;
					monsterhealth -= num;
				}
				else {
					num = rand() % 5 + 2; //range from 2-7
					cout << "you punch the sigma wolf with your sword for" << num << "dmg" << endl;
					monsterhealth -= num;

					cout << "you hit the sigma wolf for 17 dmg" << endl;
					monsterhealth -= 10;
				}
				break;
			case 2: // health potion
				if (items[3] == "coca cola") {
					cout << "glug glug !" << endl;
					playerhealth += 50;
					items[3] = " "; //erase the potion

				}
				else cout << " sorry, you dont have any tonics." << endl;

				break;
			case 3: // escape
				num = rand() & 100;
				if (num > 75) {//25% chance of escaping
					cout << "you successfully run away!" << endl;
					monsterhealth = 0;
				}



				break;

			case 4: // health potion
				if (items[4] == "maple syrup") {
					cout << "glug glug !" << endl;
					playerhealth += 50;
					items[4] = " "; //erase the potion

				}
				else cout << " sorry, you dont have any tonics." << endl;

				break;

			case 5:
				//player attack
				if (items[0] == "igloo thrower") {
					num = rand() % 10 + 10; // range from 10-20
					cout << "you throw a igloo at the sigma wolf with your weapon for " << num << " damge!" << endl;
					monsterhealth -= num;
				}
				else {
					num = rand() % 5 + 2; //range from 2-7
					cout << "you hurt the sigma wolf with your igloos for" << num << "dmg" << endl;
					monsterhealth -= num;

					cout << "you hit the sigma wolf for 25 dmg" << endl;
					monsterhealth -= 10;
				}
				break;

			default:
				cout << "sorry not an option" << endl;






				cout << "you hit the sigma wolf for 10 dmg" << endl;
				monsterhealth -= 10;

				cout << "your health:" << playerhealth << endl;
				cout << "the sigma wolf health:" << monsterhealth << endl;



			}
			if (monsterhealth < 0)
				cout << "---------------------------end of battle---------------------------" << endl;
		}
	}		if (playerhealth < 0)
		cout << "you died mane" << endl;
}

void skibiditoilet() {
	int monsterhealth = 32;
	int input;
	int num;
	cout << endl << endl << "------------GO GET THERM------------" << endl;
	while (playerhealth > 0 && monsterhealth > 0) {

		//monster attack
		if (items[1] == "basketball on fire shirt") {
			num = rand() % 7 + 3;
			cout << "your shirt  abords the blow and you get hit for {" << num << " damge!" << endl;

			playerhealth -= num;
		}

		else if (items[1] == "alphonso davies jersey") {
			num = rand() % 8 + 5;
			cout << "your jersey  abords the blow and you get hit for {" << num << " damge!" << endl;

			playerhealth -= num;
		}

		else {
			num = rand() % 15 + 12;
			cout << "skibidi toilet shoots fire toilets at you for" << num << "dmg" << endl;
			playerhealth -= num;


			cout << "skibidi toilet shoots fire toilets at you for 25 dmg" << endl;
			playerhealth -= 15;

			//get players choice:
			cout << "press 1 to attack, 2 to drink health tonic, 3 to try to escape!" << endl;
			cin >> input;

			switch (input) {
			case 1:
				//player attack
				if (items[0] == "elote") {
					num = rand() % 10 + 20; // range from 10-20
					cout << "you slash skibidi toilet with your weapon for " << num << " damge!" << endl;
					monsterhealth -= num;
				}
				else {
					num = rand() % 9 + 18; //range from 2-7
					cout << "you punch skibidi toilet with your sword for" << num << "dmg" << endl;
					monsterhealth -= num;

					cout << "you hit skibidi toilet  for 17 dmg" << endl;
					monsterhealth -= 17;
				}
				break;
			case 2: // health potion
				if (items[3] == "coca cola") {
					cout << "glug glug !" << endl;
					playerhealth += 50;
					items[3] = " "; //erase the potion

				}
				else cout << " sorry, you dont have any tonics." << endl;

				break;
			case 3: // escape
				num = rand() & 100;
				if (num > 75) {//25% chance of escaping
					cout << "you successfully run away!" << endl;
					monsterhealth = 0;
				}



				break;

			case 4: // health potion
				if (items[4] == "maple syrup") {
					cout << "glug glug !" << endl;
					playerhealth += 50;
					items[4] = " "; //erase the potion

				}
				else cout << " sorry, you dont have any tonics." << endl;

				break;

			case 5:
				//player attack
				if (items[0] == "igloo thrower") {
					num = rand() % 10 + 10; // range from 10-20
					cout << "you throw a igloo at skibidi toilet with your weapon for " << num << " damge!" << endl;
					monsterhealth -= num;
				}
				else {
					num = rand() % 5 + 2; //range from 2-7
					cout << "you hurt skibidi toilet with your igloos for" << num << "dmg" << endl;
					monsterhealth -= num;

					cout << "you hit skibidi toilet for 25 dmg" << endl;
					monsterhealth -= 10;
				}
				break;

			default:
				cout << "sorry not an option" << endl;






				cout << "you hit skibidi toilet for 10 dmg" << endl;
				monsterhealth -= 10;

				cout << "your health:" << playerhealth << endl;
				cout << "Skibidi toilet health:" << monsterhealth << endl;



			}
			if (monsterhealth < 0)
				cout << "---------------------------end of battle---------------------------" << endl;
		}	if (playerhealth < 0)
			cout << "you died mane" << endl;
	}
}
