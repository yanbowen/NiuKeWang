	package niukewang;
	
	/*
	 * 题目描述
	 * 		输入一个正整数n,求n!(即阶乘)末尾有多少个0？ 比如: n = 10; n! = 3628800,所以答案为2
	 * */
	import java.util.Scanner;
	
	public class A22_DaWeiShuJieCeng {
	
		public static void main(String[] args) {
	
			Scanner scanner = new Scanner(System.in);
			int n = scanner.nextInt();
			int num5 = 0;
	
			for (int i = 5; i <= n; i++) {
				int temp = i;
				while (temp % 5 == 0) {
					num5++;
					temp = temp / 5;
				}
			}
			scanner.close();
			System.out.println(num5);
		}
	}
