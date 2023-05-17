  public static boolean solveSudoku(int[][] puzzle) {
        for (int row = 0; row < 9; row++) {
            for (int col = 0; col < 9; col++) {
                if (puzzle[row][col] == 0) {
                    for (int num = 1; num <= 9; num++) {
                        if (isValidMove(puzzle, row, col, num)) {
                            puzzle[row][col] = num;
                            if (solveSudoku(puzzle)) {
                                return true;
                            }
                            puzzle[row][col] = 0;
                        }
                    }
                    return false;
                }
            }
        }
