# pascal-triangle-using-c
#include <iostream>
using namespace std;

int main() {
    int rows;

    cout << "Enter the number of rows for Pascal's Triangle: ";
    cin >> rows;

    // Create and initialize Pascal's Triangle
    int pascalTriangle[rows][rows];

    for (int i = 0; i < rows; i++) {
        for (int j = 0; j <= i; j++) {
            if (j == 0 || j == i) {
                pascalTriangle[i][j] = 1;
            } else {
                pascalTriangle[i][j] = pascalTriangle[i - 1][j - 1] + pascalTriangle[i - 1][j];
            }
        }
    }

    // Display Pascal's Triangle
    for (int i = 0; i < rows; i++) {
        // Add spaces to center the triangle
        for (int space = 0; space < rows - i - 1; space++) {
            cout << " ";
        }

        for (int j = 0; j <= i; j++) {
            cout << pascalTriangle[i][j] << " ";
        }

        cout << endl;
    }

    return 0;
}
