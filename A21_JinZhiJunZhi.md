	package niukewang;
	
	/*
	 * 题目描述:
	 * 
	 * 如十进制数123表达为16进制时只包含两位数7、11（B），用八进制表示为三位数1、7、3，按不同进制表达时，
	 * 各个位数的和也不同，如上述例子中十六进制和八进制中各位数的和分别是18和11,。 
	 * 小B感兴趣的是，一个数A如果按2到A-1进制表达时，各个位数之和的均值是多少？她希望你能帮她解决这个问题？
	 *  所有的计算均基于十进制进行，结果也用十进制表示为不可约简的分数形式。
	 *  
	 *  输入
	 *   5		 3
	 *  输出
	 *  7/3		2/1
	 * */
	import java.util.Scanner;
	
	public class A21_JinZhiJunZhi {
		public static void main(String[] arg) {
			Scanner scanner = new Scanner(System.in);
			int A = scanner.nextInt();
			int sum = 0;
			for (int i = 2; i <= A - 1; i++) {
				int num = getNum(A, i);
				sum = sum + num;
			}
			int commonMax = getMaxCommon(sum, A - 2);
			System.out.println(sum / commonMax + "/" + (A - 2) / commonMax);
			scanner.close();
		}
	
		// 各个进制位数之和
		public static int getNum(int A, int i) {
			int sum = 0;
			while (A != 0) {
				sum += A % i;
				A = A / i;
			}
			return sum;
		}
	
		// 最大公约数
		public static int getMaxCommon(int a, int b) {
			int temp;
			while (b != 0) {
				temp = a;
				a = b;
				b = temp % b;
			}
			return a;
		}
	}
