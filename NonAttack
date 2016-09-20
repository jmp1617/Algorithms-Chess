/**
 * Created by Jacob on 2/10/2016.
 */
public class NonAttackingQueens {
    private static char[][] board = new char[16][16];
    final static char QUEEN = 'Q';
    final static char EMPTY = ' ';

    public static void populateBoard(char cha){
        for (int r = 0; r < board.length; r++)
            for (int c = 0; c < board[r].length; c++)
                board[r][c] = cha;
    }

    public static void printBoard(){
        for(int x = 0; x <board.length*2+1;x++)
            System.out.print("-");
        System.out.println();
        for(int r =0; r<board.length; r++) {
            for (int c = 0; c < board[r].length; c++) {
                System.out.print("|"+board[r][c]);
            }
            System.out.println("|");
        }
        for(int x = 0; x <board.length*2+1;x++)
            System.out.print("-");
        System.out.println();
    }

    static boolean solve(int row, int N) {
        if(row>=N) {
            printBoard();
            return true;
        }
        for(int position = 0; position < N; position++) {
            if(isValid(row,position)){
                board[row][position] = QUEEN;
                if(!solve(row+1, N))
                    board[row][position] = EMPTY;
                else
                    return true;
            }
        }
        return false;
    }

    public static boolean isValid(int row, int col){
        if(isVerticle(row,col)&&isDiagonal(row,col))
            return true;
        else return false;
    }

    public static boolean isVerticle(int row, int col){ //check if it is safe up
        boolean safe = true;
        while (row>=0){
            if(board[row--][col]==QUEEN)
                safe = false;
        }
        return safe;
    }

    public static boolean isDiagonal(int row, int col){ //check if it is safe in diagonals
        boolean safeLeft = true;
        boolean safeRight = true;
        int rowLeft = row, rowRight = row;
        int colLeft = col, colRight = col;
        while (rowLeft>=0&&colLeft>=0){
            if(board[rowLeft--][colLeft--]==QUEEN)
                safeLeft = false;
        }
        while (rowRight>=0&&colRight<=board.length-1){
            if(board[rowRight--][colRight++]==QUEEN)
                safeRight = false;
        }
        if(safeLeft&&safeRight)
            return true;
        else return false;
    }

    public static void main(String[] args) {
        populateBoard(EMPTY);
        solve(0,16);
    }
}
