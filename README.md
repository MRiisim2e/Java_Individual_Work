# Java_Individual_Work

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        int[][] grid = new int[3][3];
        Scanner scanner = new Scanner(System.in);

        for (int i = 0; i < grid.length; i++) {
            for (int j = 0; j < grid[i].length; j++) {
                grid[i][j] = 0;
            }
        }

        // Game loop
        while (true) {
            // Print the current grid
            printGrid(grid);

            // Ask the user for row and column numbers
            System.out.print("Enter the row number (0-2): ");
            int row = scanner.nextInt();
            System.out.print("Enter the column number (0-2): ");
            int col = scanner.nextInt();

            // Check if the selected cell is already filled
            if (grid[row][col] == 1) {
                System.out.println("This cell is already filled. Try again.");
                continue;
            }

            // Set the cell to 1
            grid[row][col] = 1;

            // Check if the row contains all 1s
            boolean rowWin = true;
            for (int i = 0; i < 3; i++) {
                if (grid[row][i] != 1) {
                    rowWin = false;
                    break;
                }
            }

            // If the row contains all 1s, the player wins
            if (rowWin) {
                System.out.println("Congratulations! You won!");
                printGrid(grid);
                break;
            }
        }

        scanner.close();
    }

    // Method to print the grid
    public static void printGrid(int[][] grid) {
        for (int i = 0; i < grid.length; i++) {
            for (int j = 0; j < grid[i].length; j++) {
                System.out.print(grid[i][j] + " ");
            }
            System.out.println();

            }
        }
    }
```
