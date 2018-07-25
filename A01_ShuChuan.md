	package niukewang;
	
	/*题目描述
	设有n个正整数，将他们连接成一排，组成一个最大的多位整数。
	如:n=3时，3个整数13,312,343,连成的最大整数为34331213。
	如:n=4时,4个整数7,13,4,246连接成的最大整数为7424613。
	*/
	import java.util.Scanner;
	import java.util.Arrays;
	
	public class A01_ShuChuan {
	
		public static void main(String[] args) {
	
			Scanner scanner = new Scanner(System.in);
			int N = scanner.nextInt();
			int arr[] = new int[N];
			for (int i = 0; i < arr.length; i++) {
				arr[i] = scanner.nextInt();
			}
	
			System.out.println(Arrays.toString(arr));
	
			for (int i = 0; i < arr.length - 1; i++) {
				for (int j = i + 1; j < arr.length; j++) {
	
					if (compare(arr, i, j)) {
	
						int temp = arr[i];
						arr[i] = arr[j];
						arr[j] = temp;
					}
				}
			}
			for (int i = 0; i < arr.length; i++) {
				System.out.print(arr[i]);
			}
	
			scanner.close();
		}
	
		private static boolean compare(int[] arr, int i, int j) {
			String ij = String.valueOf(arr[i]) + String.valueOf(arr[j]);
			String ji = String.valueOf(arr[j]) + String.valueOf(arr[i]);
			// Java中字符串的比较函数，compareTo() 的返回值是int, 它是先比较对应字符的大小(ASCII码顺序)，
			// 阿拉伯数字组成的字符串比较与数值大小比较结果一样
			// 前字符串的值小于后字符串返回负值，前字符串大于后字符串返回正值
			if (ij.compareTo(ji) > 0)
				return false;
			else
				return true;
		}
	}
