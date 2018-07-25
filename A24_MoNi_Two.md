	package niukewang;
	
	/*
	 * 最近天气太热了，牛牛每天都要吃雪糕。雪糕有一盒一份、一盒两份、一盒三份这三种包装，
	 * 牛牛一天可以吃多盒雪糕，但是只能吃六份，吃多了就会肚子疼，吃少了就会中暑。
	 * 而且贪吃的牛牛一旦打开一盒雪糕，就一定会把它吃完。请问牛牛能健康地度过这段高温期么？ 
	 * 
	 * 输入描述:
	 * 		每个输入包含多个测试用例。
	 * 		输入的第一行包括一个正整数，表示数据组数T(1<=T<=100)。
	 * 		接下来N行，每行包含四个正整数，表示高温期持续的天数N(1<=N<=10000)，
	 * 		一盒一份包装的雪糕数量A(1<=A<=100000)，一盒两份包装的雪糕数量B(1<=B<=100000)，
	 * 		一盒三份包装的雪糕数量C(1<=A<=100000)。
	 * 
	 * 输出描述:
	 * 		对于每个用例，在单独的一行中输出结果。如果牛牛可以健康地度过高温期则输出"Yes"，否则输出"No"。
	 * 
	 * 输入例子1:
				4 
				1 1 1 1 
				2 0 0 4 
				3 0 2 5 
				4 24 0 0
	 * 输出例子1:
				Yes 
				Yes 
				No 
				Yes
	 * */
	import java.util.Scanner;
	
	public class A24_MoNi_Two {
		public static void main(String[] args) {
			Scanner in = new Scanner(System.in);
			int T = in.nextInt();
			int[][] array = new int[T][4];
			for (int i = 0; i < T; i++) {
				array[i][0] = in.nextInt();
				array[i][1] = in.nextInt();
				array[i][2] = in.nextInt();
				array[i][3] = in.nextInt();
			}
			foo(array);
		}
	
		public static void foo(int[][] arr) {
			System.out.println(arr.length);
			for (int i = 0; i < arr.length; i++) {
				while (true) {
					if (arr[i][0] == 0) {
						System.out.println("Yes");
						break;
					} else if (arr[i][0] == -1) {
						System.out.println("No");
						break;
					}
					arr[i] = cal(arr[i]);
				}
			}
		}
	
		public static int[] cal(int[] ar) {
			if (ar[3] >= 2) {
				ar[3] -= 2;
				ar[0] -= 1;
			} else if (ar[3] == 1 && ar[2] >= 1 && ar[1] >= 1) {
				ar[3] -= 1;
				ar[2] -= 1;
				ar[1] -= 1;
				ar[0] -= 1;
			} else if (ar[3] == 1 && ar[2] == 0 && ar[1] >= 3) {
				ar[3] -= 1;
				ar[1] -= 3;
				ar[0] -= 1;
			} else if (ar[3] == 0 && ar[2] >= 3) {
				ar[2] -= 3;
				ar[0] -= 1;
			} else if (ar[3] == 0 && ar[2] == 2 && ar[1] >= 2) {
				ar[2] -= 2;
				ar[1] -= 2;
				ar[0] -= 1;
			} else if (ar[3] == 0 && ar[2] == 1 && ar[1] >= 4) {
				ar[2] -= 1;
				ar[1] -= 4;
				ar[0] -= 1;
			} else if (ar[3] == 0 && ar[2] == 0 && ar[1] >= 6) {
				ar[1] -= 6;
				ar[0] -= 1;
			} else {
				ar[0] = -1;
			}
			return ar;
		}
	}
