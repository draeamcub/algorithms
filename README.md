# algorithms

import java.util.Scanner;
import java.util.*;
public class Main{
    public static boolean check1(int a[][], int n, int x, int y) {
        for (int j = 0; j < n; j++)
            if (a[x][j] > a[x][y])
                return false;
        return true;
    }
    public static boolean check2(int a[][], int n, int x, int y) {
        for (int i = 0; i < n; i++)
            if (a[i][y] > a[x][y])
                return false;
        return true;
    }
    public static boolean check3(int a[][], int n, int x, int y) {
        for (int k = Math.max(-x, -y); k <= Math.min(n - x - 1, n - y - 1); k++)
            if (a[x + k][y + k] > a[x][y])
                return false;
        return true;
    }
    public static boolean check4(int a[][], int n, int x, int y) {
        for (int k = Math.max(-x, - n + y + 1); k <= Math.min(n - x - 1, y); k++)
            if (a[x + k][y - k] > a[x][y])
                return false;
        return true;
    }
    /*public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int dong = sc.nextInt();
        int cot = sc.nextInt();
        int matrix[][] = new int[dong][cot];

        //nhập ma trận
        for(int i=0; i<dong; i++){
            for(int j=0; j<cot; j++){
                matrix[i][j] = sc.nextInt();
            }
        }

        int maxEvenCount = -1;
        int maxEvenRow = -1;

        for (int i = 0; i < dong; i++) {
            int evenCount = 0;
            for (int j = 0; j < cot; j++) {
                if (matrix[i][j] % 2 == 0) {
                    evenCount++;
                }
            }
            if (evenCount > maxEvenCount) {
                maxEvenCount = evenCount;
                maxEvenRow = i;
            }
        }

        int ans = maxEvenRow;
        for (int i = 0; i < dong; i++) {
            int evenCount = 0;
            for (int j = 0; j < cot; j++) {
                if (matrix[i][j] % 2 == 0) {
                    evenCount++;
                }
            }
            if (evenCount == maxEvenCount && i < ans) {
                ans = i;
            }
        }

        System.out.println(ans);
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int oddNum = 1;
        if(n%2!=0){
            oddNum = 2*n;
            System.out.println(oddNum);
        }else {
            System.out.println(n);
        }
    }
}




