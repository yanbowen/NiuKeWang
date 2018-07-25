	package niukewang;
	
	/*
	 题目描述
	数列的第一项为n，以后各项为前一项的平方根，求数列的前m项的和。
	输出描述:
	对于每组输入数据，输出该数列的和，每个测试实例占一行，要求精度保留2位小数。
	 */
	import java.text.DecimalFormat;
	import java.util.Scanner;
	
	public class A05_QiuShuLieDeHe {
	
		public static void main(String[] args) {
			Scanner scanner = new Scanner(System.in);
			int n = scanner.nextInt();
			int m = scanner.nextInt();
			double sum = n;
			double num = n;
			// 方法一：最简便的方法，调用DecimalFormat类
			DecimalFormat df = new DecimalFormat(".00");
	
			for (int i = 1; i < m; i++) {
				num = Math.sqrt(num);
				sum = sum + num;
			}
			System.out.println(df.format(sum));
			// 方法二
			// System.out.printf("%.2f\n", sum);
			scanner.close();
		}
	}
