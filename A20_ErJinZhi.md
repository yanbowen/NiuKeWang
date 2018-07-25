	package niukewang;
	
	import java.util.Scanner;
	
	/*
	 * 题目描述
	 * 		现在对于一个数字x，小明同学定义出了两个函数f(x)和g(x)。 
	 * 		f(x)表示把x这个数用十进制写出后各个数位上的数字之和。
	 * 		如f(123)=1+2+3=6。 g(x)表示把x这个数用二进制写出后各个数位上的数字之和。
	 * 		如123的二进制表示为1111011，那么，g(123)=1+1+1+1+0+1+1=6。 
	 * 		小明同学发现对于一些正整数x满足f(x)=g(x)，他把这种数称为幸运数，
	 * 		现在他想知道，小于等于n的幸运数有多少个？
	 * */
	public class A20_ErJinZhi {
		public static void main(String[] args) {
			Scanner sc = new Scanner(System.in);
			int n = sc.nextInt();
			int num = 0;
			while (n != 0) {
				if (get10(n) == get2(n)) {
					num++;
				}
				n--;
			}
			System.out.println(num);
			sc.close();
		}
	
		private static int get10(int n) {
			int num = 0;
			while (n != 0) {
				num += n % 10;
				n = n / 10;
			}
			return num;
		}
	
		private static int get2(int n) {
			int num = 0;
			while (n != 0) {
				num += n % 2;
				n = n / 2;
			}
			return num;
		}
	}
