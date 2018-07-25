	package niukewang;
	
	/*
	 * 题目描述
	 * 		有一个X*Y的网格，小团要在此网格上从左上角到右下角，只能走格点且只能向右或向下走。
	 * 		请设计一个算法，计算小团有多少种走法。给定两个正整数int x,int y，请返回小团的走法数目。
	 * 算法
	 * 		这是一个典型的递归算法问题，因为每次走法必须是往右或者是往下，因此不管是到达那个点，
	 * 		它的必经之路一定是它上方或者左方相邻的那个点，因此可以得出一个递归表达式：
	 * 		f[m][n]=f[m-1][n]+f[m][n-1]；这个递归表达式的条件为m,n都不为0的时候，
	 * 		除了这个表达式还需要写出一个已知条件，f[0][0] = 0;f[{1->m}][0] = 1;f[0][{1->n}] = 1;
	 * 		这样就可以解出最终f[m][n]的值了
	 * */
	import java.util.Scanner;
	
	public class A19_WangGeZouFa {
	
		public static void main(String[] args) {
	
			Scanner scanner = new Scanner(System.in);
			int m = scanner.nextInt();
			int n = scanner.nextInt();
	
			int num = getGrid(m, n);
			System.out.println(num);
			scanner.close();
	
		}
	
		public static int getGrid(int m, int n) {
	
			if (m == 0 || n == 0) {
				return 1;
			}
			return (getGrid(m - 1, n) + getGrid(m, n - 1));
		}
	}
