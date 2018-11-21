	package niukewang;
	
	import java.util.Scanner;
	
	/*
	 *  题目描述:
	 *  
	 *  一只袋鼠要从河这边跳到河对岸，河很宽，但是河中间打了很多桩子，每隔一米就有一个，
	 *  每个桩子上都有一个弹簧，袋鼠跳到弹簧上就可以跳的更远。每个弹簧力量不同，用一个数字代表它的力量，
	 *  如果弹簧力量为5，就代表袋鼠下一跳最多能够跳5米，如果为0，就会陷进去无法继续跳跃。河流一共N米宽，
	 *  袋鼠初始位置就在第一个弹簧上面，要跳到最后一个弹簧之后就算过河了，给定每个弹簧的力量，
	 *  求袋鼠最少需要多少跳能够到达对岸。如果无法到达输出-1
	 */
	public class A06_DaiShuGuoHe {
	
		public static void main(String[] args) {
			Scanner scanner = new Scanner(System.in);
			int N = scanner.nextInt();
			int arr[] = new int[N];
			for (int i = 0; i < N; i++) {
				arr[i] = scanner.nextInt();
			}
	
			int len = minStep(arr);
			System.out.println(len);
			scanner.close();
		}
	
		private static int minStep(int[] arr) {
			int sum = 0;// 总步数
			for (int i = 0; i < arr.length;) {
				// 如果到了最后一个柱子，判断能否到岸
				if (i == arr.length - 1 && arr[i] != 0) {
					sum++;
					break;
				}
				int maxLen = 0, p = 0;// maxLen代表能跳最远的柱子，p指向最远柱子的下标
				for (int j = i + 1; j <= i + arr[i]; j++) {
					int l = j - i + arr[j];// 计算最远能跳的距离
					if (l >= maxLen) {
						maxLen = l;
						p = j;// p指向当前最远柱子坐标
					}
				}
				// 若最远的柱子值为0,不能上岸
				if (arr[i] == 0 || p == 0) {
					return -1;
				}
	
				i = p;// 否则跳到p指向的最远坐标
				++sum;// 步数++
						// 判断是否一步就能上岸
				if (p + arr[p] > arr.length - 1) {
					++sum;
					break;
				}
			}
			return sum;
		}
	}
