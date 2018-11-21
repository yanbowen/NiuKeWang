	package niukewang;
	
	/*
	 * 题目描述:
	 * 
	 * 春天是鲜花的季节，水仙花就是其中最迷人的代表，数学上有个水仙花数，他是这样定义的： 
	 * “水仙花数”是指一个三位数，它的各位数字的立方和等于其本身，比如：153=1^3+5^3+3^3。 
	 * 现在要求输出所有在m和n范围内的水仙花数。
	 * 注意输出前后空格去掉 str.trim();
	 */
	import java.util.Scanner;
	
	public class A04_ShuiXianHuaShu {
	
		public static void main(String[] args) {
	
			int arr[] = new int[3];
			boolean flag = true;
	
			Scanner scanner = new Scanner(System.in);
			int m = scanner.nextInt();
			int n = scanner.nextInt();
			String str = "";
	
			for (int i = m; i <= n; i++) {
				getNum(arr, i);
				if (i == (Math.pow(arr[0], 3) + Math.pow(arr[1], 3) + Math.pow(arr[2], 3))) {
	
					str = str + i + " ";
					flag = false;
				}
			}
			if (flag)
				System.out.println("no");
			else
				System.out.println(str.trim());
			scanner.close();
		}
	
		private static void getNum(int[] arr, int num) {
	
			int a = num / 100;
			int b = (num - ((num / 100) * 100)) / 10;
			arr[0] = a;
			arr[1] = b;
			arr[2] = num - a * 100 - b * 10;
		}
	}
