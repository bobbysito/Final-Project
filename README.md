# Final-Project
#include <iostream>
#include <conio.h>
#include <windows.h>
#include <stdlib.h>
using namespace std;

char input_key_easy;
char input_key_medium;
char input_key_hard;

void menu();
void draw_maze_easy();
void draw_maze_medium();
void draw_maze_hard();
void character_movement_easy();
void character_movement_medium();
void character_movement_hard();
void gotoXY(int x, int y);

 //*Int main displays the the menu onto the screen
int main()
{
  menu();
  return 0;
}
void menu()
{
char selection;

cout << " Maze Game Menu" << endl;
cout << "-------------------" << endl;
cout << " " << endl;
cout << " Choose your difficulty" << endl;
cout << "------------------------" << endl;
cout << " 1: Easy" << endl;
cout << " 2: Medium" << endl;
cout << " 3: Hard" << endl;
cout << " 4: Exit" << endl;
cout << " " << endl;
cout << " Enter selection: \n";
cin >> selection;
cin.ignore();

  if(selection == '1')
  {
    system("cls");
    draw_maze_easy();
    character_movement_easy();
  }

  if(selection == '2')
  {
    system("cls");
    draw_maze_medium();
    character_movement_medium();
  }

  if(selection == '3')
  {
    system("cls");
    draw_maze_hard();
  }

  if (selection == '4')
  {
    exit(1);
  }

   if(selection != '1' && '2' && '3' && '4')
  {
    cout << "\nPlease re-enter: ";
    cin >> selection;

    if(selection == '1')
    {
      draw_maze_easy();
      character_movement_easy();
    }

    if(selection == '2')
    {
      draw_maze_medium();
    }

    if(selection == '3')
    {
      draw_maze_hard();
    }

    if (selection == '4')
    {
      exit(1);
    }
  }
}

void gotoXY(int x, int y)
{
    COORD coord;
    coord.X = x;
    coord.Y = y;
    SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE), coord);
}

int maze_map_easy [21][31] =
{

// 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9
  {1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1},
  {1,1,0,0,0,0,0,0,0,1,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,1},
  {1,1,0,1,1,0,1,1,1,1,1,1,1,1,1,0,1,1,1,1,1,1,1,1,1,1,1,1,0,1,1},
  {1,1,0,1,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,1,1,0,1,1,0,1,1},
  {1,1,0,1,1,0,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,0,0,0,0,1,1},
  {1,1,0,1,1,0,1,1,0,0,0,0,0,0,0,1,1,0,0,0,0,0,0,1,1,0,1,1,0,1,1},
  {1,1,0,1,1,0,1,1,0,1,1,1,1,1,1,1,1,1,1,1,1,1,0,0,0,0,1,1,0,1,1},
  {1,1,0,1,1,0,0,0,0,1,1,0,0,0,0,0,0,0,0,0,1,1,0,1,1,0,1,1,0,1,1},
  {1,1,0,1,1,1,1,1,0,1,1,0,1,1,1,1,1,1,1,0,1,1,0,1,1,0,1,1,1,1,1},
  {1,1,0,1,1,0,1,1,1,1,1,0,1,1,0,0,0,1,1,0,1,1,0,1,1,1,1,1,0,1,1},
  {1,1,0,1,1,0,1,1,0,1,1,1,1,1,0,0,0,1,1,0,0,0,0,1,1,0,1,1,0,1,1},
  {1,1,0,1,1,0,1,1,0,1,1,0,1,1,0,0,0,1,1,0,1,1,0,1,1,0,1,1,0,1,1},
  {1,1,0,1,1,0,0,0,0,1,1,0,1,1,1,0,1,1,1,0,1,1,0,1,1,0,1,1,0,1,1},
  {1,1,0,1,1,0,1,1,0,1,1,0,0,0,0,0,0,0,0,0,1,1,0,1,1,0,0,0,0,1,1},
  {1,1,0,1,1,0,1,1,0,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,0,1,1,0,1,1},
  {1,1,0,1,1,0,1,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,1,0,1,1,0,1,1},
  {1,1,0,0,0,0,1,1,1,1,1,1,1,1,1,0,1,1,1,1,1,1,1,1,1,0,1,1,0,1,1},
  {1,1,0,1,1,0,0,0,0,1,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,1,0,1,1},
  {1,1,0,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,0,1,1},
  {1,1,0,0,0,0,1,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,1},
  {1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,2,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1}

};

// Function Prototype

void draw_maze_easy()
{
      // This loop will increment until it reaches twenty-one because it is the vertical line
  for (int v = 0; v < 21; v++)
  {
    // This loop will increment until it reaches thirty-one because it is the horizontal line
    for (int h = 0; h < 31; h++)
    {
      switch (maze_map_easy[v][h])
      {
        // These cases are defining what the numbers mean
        // The break breaks the switch
        case 0:
             cout << " ";
             break;
        case 1:
             // Char 219 is simply a block
             cout << char(219);
             break;
        case 2:
             cout << " ";
             break;
      }
    }
   cout << endl;
  }
}
