import org.jetbrains.annotations.Contract;

import java.util.Scanner;

/**
 * 
 * Created by Jacob on 2/15/2016.
 */ 
public class KnightTour {
    public static int N = 5;
    private static int[][] board = new int[N][N];
    //moves for a knight
    private static int xMove[] = {2, 1, -1, -2, -2, -1, 1, 2};
    private static int yMove[] = {1, 2, 2, 1, -1, -2, -2, -1};
    public static int startx = 0;
    public static int starty = 0;

    @Contract(pure = true)
    public static boolean isSafe(int x, int y) {
        return (x >= 0 && x < N && y >= 0 && y < N && board[x][y] == -1);
    }

    public static void printBoard() {
        String spacer;
        for (int x = 0; x < N; x++) {
            for (int y = 0; y < N; y++) {
                if (board[x][y] >= 9)
                    spacer = "   ";
                else
                    spacer = "    ";
                System.out.print(board[x][y]+1 + spacer);
            }
            System.out.println();
        }
        System.out.println();
    }

    public static void populate(){
        for (int x = 0; x < N; x++)
            for (int y = 0; y < N; y++)
                board[x][y] = -1;
    }

    public static boolean solve(int x, int y, int moveNum) {
        if (moveNum == N * N)
            return true;
        for (int moveSet = 0; moveSet < 8; moveSet++) {
            int next_x = x + xMove[moveSet];
            int next_y = y + yMove[moveSet];
            if (isSafe(next_x, next_y)) {
                board[next_x][next_y] = moveNum;
                //printBoard();
                if (solve(next_x, next_y, moveNum + 1))
                    return true;
                else
                    board[next_x][next_y] = -1;// backtracking
            }
        }
        return false;
    }

    public static void main(String args[]) {
        Scanner scan = new Scanner(System.in);
        System.out.print("Enter the start x: 0-"+(N-1)+": ");
        startx=scan.nextInt();
        System.out.print("Enter the start y: 0-"+(N-1)+": ");
        starty=scan.nextInt();
        populate();
        board[startx][starty] = 0;
        if (!solve(startx,starty,1)) {
            System.out.println("Solution does not exist");
        } else
            printBoard();
    }
}
