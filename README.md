//https://roadmap.sh/projects/number-guessing-game
#include <iostream>
#include <stdlib.h>
#include <Windows.h>
#include <string>
using namespace std;
int main()
{   srand(time(NULL));
    SetConsoleOutputCP(1251);
    SetConsoleCP(1251);
    int player = 0, answer = 1 + rand() % 100;
    cout << "Ласкаво просимо до гри «Вгадай число»! " << endl;
    while (true) {
        cout << "Виберіть рівень складності: \n 1. Легко (10 шансів) \n 2. Середній (5 шансів) \n 3. Важко (3 шанси)" << endl;
        int level = 0, chances = 0;
        while (true) {
            cin >> level;
            if (level == 1) {
                chances = 10;
                cout << "Чудово! Ви вибрали легкий рівень складності. У Вас 10 спроб. Починаємо гру!" << endl;
                break;
            }
            else if (level == 2) {
                chances = 5;
                cout << "Чудово! Ви вибрали середній рівень складності. У Вас 5 спроб. Починаємо гру!" << endl;
                break;
            }
            else if (level == 3) {
                chances = 3;
                cout << "Чудово! Ви вибрали важкий рівень складності. У Вас 3 спроби. Починаємо гру!" << endl;
                break;
            }
            else {
                cout << "Ви ввели невірне число" << endl;
            }
        }
        cout << "Я загадав про число від 1 до 100." << endl;
        for (int i = 1; i <= chances; i++) {
            cout << "Спроба №" << i << ":" << endl;
            cout << "Введіть ваше число: ";
            cin >> player;
            if (player == answer) {
                cout << "Ви вгадали за "<< i << " спроб." << endl;
                break;
            }
            else if (player > answer) { cout << "Число завелике" << endl ; }
            else if (player < answer) { cout << "Число замаленьке" << endl ; }
        }
        if (player != answer) { cout << "Ви програли" << endl; }
        cout << endl;
        cout << "Якщо хочете зіграти ще раз напишіть \"yes\"" << endl;
        string check = "yes";
        cin >> check;
        if (check != "yes") {
            cout << "Дякую за гру."; 
            break;
        }
        else {
            cout << endl << "Добре, починаємо нову гру." << endl << endl << endl;
        }
    }
    return 0;
} 
