#include <iostream>
#include <conio.h>
#include <Windows.h>
#include <string>
using namespace std;
struct movement
{
    char right = 'd', up = 'w', down = 's', left = 'a';
};
void PrintStruct(movement action)
{
    cout << "\nДействия:\n"
        << action.up << "- Вверх\n"
        << action.down << "- Вниз\n"
        << action.left << "- Влево\n"
        << action.right << "- Вправо\n"
        << "Или нажмите Esc чтобы выйти из игры\n";
}
movement scanStruct(movement action)
{
    char right, up, down, left;
    cout << "\n Введите новый параметр движения вверх: ";
    cin >> up;
    cout << "\n Введите новый параметр движения вниз: ";
    cin >> down;
    cout << "\n Введите новый параметр движения влево: ";
    cin >> left;
    cout << "\n Введите новый параметр движения вправо: ";
    cin >> right;
    action.up = up;
    action.down = down;
    action.left = left;
    action.right = right;
    return action;
}
int main()
{
    setlocale(LC_ALL, "Russian");
    movement action;
    movement up, down, left, right;
    int menu = 0;
    int cho = 0;
    int cont = 1;
    while (cont == 1)
    {
        cout << "Добро пожаловать на остров.\n"
            << "Пожалуйста выберите пункт из меню чтобы перейти к нему\n";
        cout << "1 - Начать игру\n"
            << "2 - Настройки\n"
            << "3 - Выход из игры\n";
        while (cho == 0)
        {
            cin >> menu;
            if ((cin.good()) && (menu == 1) || (menu == 2) || (menu == 3))
            {
                cho = 1;
            }
            else
            {
                cin.clear();
                cin.ignore(100, '\n');
                cho = 0;
                cout << "Выберите пожалуйста пункты из меню.\n";
            }
        }
        cho = 0;
        switch (menu)
        {
        case 1:
        {
            #include <iostream>

struct movement
{
    char right = 'd', up = 'w', down = 's', left = 'a';
};
void PrintStruct(movement action)
{
    cout << "\nДействия:\n"
        << action.up << "- Вверх\n"
        << action.down << "- Вниз\n"
        << action.left << "- Влево\n"
        << action.right << "- Вправо\n"
        << "Или нажмите Esc чтобы выйти из игры\n";
}
movement scanStruct(movement action)
{
    char right, up, down, left;
    cout << "\n Введите новый параметр движения вверх: ";
    cin >> up;
    cout << "\n Введите новый параметр движения вниз: ";
    cin >> down;
    cout << "\n Введите новый параметр движения влево: ";
    cin >> left;
    cout << "\n Введите новый параметр движения вправо: ";
    cin >> right;
    action.up = up;
    action.down = down;
    action.left = left;
    action.right = right;
    return action;
}
int main()
{
    setlocale(LC_ALL, "Russian");
    movement action;
    movement up, down, left, right;
    int menu = 0;
    int cho = 0;
    int cont = 1;
    while (cont == 1)
    {
        cout << "Добро пожаловать на остров.\n"
            << "Пожалуйста выберите пункт из меню чтобы перейти к нему\n";
        cout << "1 - Начать игру\n"
            << "2 - Настройки\n"
            << "3 - Выход из игры\n";
        while (cho == 0)
        {
            cin >> menu;
            if ((cin.good()) && (menu == 1) || (menu == 2) || (menu == 3))
            {
                cho = 1;
            }
            else
            {
                cin.clear();
                cin.ignore(100, '\n');
                cho = 0;
                cout << "Выберите пожалуйста пункты из меню.\n";
            }
        }
        cho = 0;
        switch (menu)
        {
        case 1:
        {
            cout << "Однажды, рывшись в старых вещах на чердаке, находите старую карту по виду которой, вы полагаете что это карта сокровищь.\n";
            cout << "Недолго думая, вы решаете, что пора что-то менять в своей серой жизни и отправляетесь на поиски богатства.\n";
            system("pause");
            char map[10][10];
            int length = sizeof(map[0]) / sizeof(map[0][0]);
            for (int i = 0; i < length; i++)
            {
                for (int j = 0; j < length; j++)
                {
                    map[i][j] = '.';
                }
            }
            map[7][7] = 'X';
            map[0][0] = 'T';
            map[9][0] = 'F';
            int plank = 0;
            int x = 0;
            int y = 1;
            int esc = 23;
            char move;
            bool win = false;
            bool lost = false;
            bool death = false;
            bool bridge = false;
            bool laziness = false;
            for (int i = 0; i < length; i++)
            {
                map[i][4] = 'R';
            }
            while (true)
            {
                system("cls");
                for (int i = 0; i < length; i++)
                {
                    for (int j = 0; j < length; j++)
                    {
                        if (x == j && y == i)
                        {
                            cout << " +";
                            if (map[i][j] == 'X')
                            {
                                win = true;
                            }
                            if ((map[i][j] == 'R') && (plank == 0))
                            {
                                death = true;
                            }
                            if (map[i][j] == 'F')
                            {
                                bridge = true;
                            }
                            if (map[i][j] == 'T')
                            {
                                laziness = true;
                            }
                        }
                        else
                        {
                            cout << ' ' << map[i][j];
                        }
                    }
                    cout << '\n';
                }
                if (win)
                {
                    cout << "Вы нашли сокровище и теперь вы владеете несметными богатствами.\n";
                    cout << "Это позволит прожить вам остаток жизни ни в чем себе не отказывая.\n";
                    return 0;
                }
                if (death)
                {
                    cout << "Вы настолько преисполнелись в своём походе, что не замечаете как заходите в реку.\n"
                        << "К сожаление у реки было сильное течение и глубое дно, и так как вы не умеете плавать, вы утонули." << endl;
                    return 0;
                }
                if (bridge)
                {
                    cout << "Вы заходите в лес, в котором находите пару бревен" << endl;
                    bridge = false;
                    plank = 1;
                }
                if (laziness)
                {
                    cout << "Вы решили, что поиск сокровищ это детские фантазии.\n";
                    cout << "Доказав, что в вас нет ни капли авантюризма.\n";
                    cout << "В результате, вас ждёт лишь серая и бедная жизнь\n";
                    return 0;
                }
                if (lost)
                {
                    cout << "Похоже иследователь из вас такой себе, поэтому вы потерялись.\n"
                        << "И вас никто уже не видел целый месяц." << endl;
                    return 0;
                }
                PrintStruct(action);
                    move = _getch();
                    if ((cin.good()) && (move == action.up) || (move == action.down) || (move == action.left) || (move == action.right) || (move == 27))
                cho = 0;
                if (move == action.up)
                {
                    if (y - 1 >= 0)
                    {
                        y--;
                    }
                }
                else if (move == action.down)
                {
                    if (y + 1 <= length)
                    {
                        y++;
                    }
                    if (y >= length)
                    {
                        lost = true;
                    }
                }
                else if (move == action.left)
                {
                    if (x - 1 >= 0)
                    {
                        x--;
                    }
                }
                else if(move == action.right)
                {
                    if (x + 1 <= length)
                    {
                        x++;
                    }
                    if (x >= length)
                    {
                        lost = true;
                    }
                }
                else if (move == 27)
                {
                    system("pause");
                    return 0;
                }
            }
        }

        case 2:
        {
            action = scanStruct(action);
            PrintStruct(action);
            menu = 0;
            continue;
        }
        case 3:
        {
            system("pause");
            return 0;
        }
        }
    }
}

        }

        case 2:
        {
            action = scanStruct(action);
            PrintStruct(action);
            menu = 0;
            continue;
        }
        case 3:
        {
            system("pause");
            return 0;
        }
        }
    }
}
