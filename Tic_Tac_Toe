#include <iostream>
#include <string>

using namespace std;

class Tic_Tac_Toe {
public:
    char block[3][3] = {{'1', '2', '3'}, {'4', '5', '6'}, {'7', '8', '9'}};
    char chance = '1';
    string player_1;
    string player_2;

    void intro() {              // It takes player name and assigns symbols to play.
        cout << "Enter the name of player 1: ";
        getline(cin, player_1);

        cout << "Enter the name of player 2: ";
        getline(cin, player_2);

        cout << "\n\n";

        cout << player_1 << " has chosen to play with 'X'." << endl;
        cout << player_2 << " has chosen to play with 'O'." << endl;
    }

    void input() {              // It takes position as input and updates array ,if one already doesn't exists.
        int pos, row, col; 

        if (chance == '1') {    // Decides whose chance to play
            cout << "\n" << player_1 << ", please enter your position to play: ";
            cin >> pos;
        } else if (chance == '2') {     // Decides whose chance to play
            cout << "\n" << player_2 << ", please enter your position to play: ";
            cin >> pos;
        }

        switch (pos) {              // Helps array to locate position from input
            case 1: row = 0; col = 0; break;
            case 2: row = 0; col = 1; break;
            case 3: row = 0; col = 2; break;
            case 4: row = 1; col = 0; break;
            case 5: row = 1; col = 1; break;
            case 6: row = 1; col = 2; break;
            case 7: row = 2; col = 0; break;
            case 8: row = 2; col = 1; break;
            case 9: row = 2; col = 2; break;
            default:        // Deals with invalid inputs
                cout << "Invalid position!\n Let's try again. " << endl;
                input(); 
                return; 
        }
        // Insertion part with exception handling (without try,throw,catch).
        if (block[row][col] != 'X' && block[row][col] != 'O') {
            if (chance == '1') {
                block[row][col] = 'X';
                chance = '2';
            } else if (chance == '2') {
                block[row][col] = 'O';
                chance = '1';
            }
        } else {
            cout << "Position already occupied!\n Let's try again. " << endl;
            input();
        }
    }

    void skele() {                  // Its game's backbone. Displaying part.
        cout << "    |    |   " << endl;
        cout << " " << block[0][0] << "  | " << block[0][1] << "  | " << block[0][2] << " " << endl;
        cout << "____|____|____" << endl;
        cout << "    |    |   " << endl;
        cout << " " << block[1][0] << "  | " << block[1][1] << "  | " << block[1][2] << " " << endl;
        cout << "____|____|____" << endl;
        cout << "    |    |   " << endl;
        cout << " " << block[2][0] << "  | " << block[2][1] << "  | " << block[2][2] << " " << endl;
        cout << "    |    |   " << endl;
    }

    bool gameover() {               // It allows us to play until its draw or one wins.
        for (int i = 0; i <= 2; i++) {
            if ((block[i][0] == block[i][1] && block[i][0] == block[i][2]) || (block[0][i] == block[1][i] && block[1][i] == block[2][i]))
                return false;
        }

        if ((block[0][0] == block[1][1] && block[0][0] == block[2][2]) || (block[0][2] == block[1][1] && block[0][2] == block[2][0]))
            return false;

        // Check for a draw
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                if (block[i][j] != 'X' && block[i][j] != 'O') {
                    return true; 
                }
            }
        }

        return false;
    }

    void winner() {                 // Declares winneer.
        for (int i = 0; i <= 2; i++) {
            if ((block[i][0] == 'X' && block[i][1] == 'X' && block[i][2] == 'X') || (block[0][i] == 'X' && block[1][i] == 'X' && block[2][i] == 'X')) {
                cout << "Congrats " << player_1 << "! you have won the game." << endl;
                return;
            } 
            else if ((block[i][0] == 'O' && block[i][1] == 'O' && block[i][2] == 'O') || (block[0][i] == 'O' && block[1][i] == 'O' && block[2][i] == 'O')) {
                cout << "Congrats " << player_2 << "! you have won the game." << endl;
                return;
            }
        }

        if ((block[0][0] == 'X' && block[1][1] == 'X' && block[2][2] == 'X') || (block[0][2] == 'X' && block[1][1] == 'X' && block[2][0] == 'X')) {
            cout << "Congrats " << player_1 << "! you have won the game." << endl;
        } 
        else if ((block[0][0] == 'O' && block[1][1] == 'O' && block[2][2] == 'O') || (block[0][2] == 'O' && block[1][1] == 'O' && block[2][0] == 'O')) {
            cout << "Congrats " << player_2 << "! you have won the game." << endl;
        } 
        else {          // If neither wins , it declares a draw.
            cout << "Good game. Its a draw!" << endl;
        }
    }
};

int main() {
    Tic_Tac_Toe play;
    play.intro();

    while (play.gameover()) {
        play.input();
        play.skele();
    }
    
    play.winner();

    return 0;
}
