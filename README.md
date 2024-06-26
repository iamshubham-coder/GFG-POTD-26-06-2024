# GFG-POTD-26-06-2024
Coverage all zeros in a binary matrix

Given a binary matrix and we need to sum of all the  sum of coverage of all zeros of the matrix where coverage for a particular 0 is defined as a total number of ones around a zero in left, right, up and bottom directions.

for ex-->
Input: 
matrix = [[0, 0, 0, 0],
          [1, 0, 0, 1], 
          [0, 1, 1, 0]]
Output: 14
explanation-->
A simple solution to solve this problem is by counting ones around zeros independently 
approach-->
we run two for loop inner and outer loop and traverse left->right&&right->left&&top->bottom&&bottom->top  
and check wheather it is one if yes then increase result variable


code-->
int findCoverage(vector<vector<int>>& matrix) {
     
     int result=0;
        int row=matrix.size();
        int col=matrix[0].size();
      
          for (int i = 0; i < row; i++) {
            for (int j = 0; j < col; j++) {
                if (matrix[i][j] == 0) {
                    // Check left
                    if (j > 0 && matrix[i][j - 1] == 1) result++;
                    // Check right
                    if (j < col - 1 && matrix[i][j + 1] == 1) result++;
                    // Check top
                    if (i > 0 && matrix[i - 1][j] == 1) result++;
                    // Check bottom
                    if (i < row - 1 && matrix[i + 1][j] == 1) result++;
                }
            }
        }

        return result;
    }
