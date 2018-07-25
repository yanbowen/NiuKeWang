	package niukewang;
	
	/*
	 * 题目描述
	 * 		现在有一个数组，其值为从1到10000的连续增长的数字。出于某次偶然操作，
	 * 		导致这个数组中丢失了某三个元素，同时顺序被打乱，现在需要你用最快的方法找出丢失的这三个元素，
	 * 		并且将这三个元素根据从小到大重新拼接为一个新数字，计算其除以7的余数。 
	 * 		例：丢失的元素为336，10，8435，得到的新数字为103368435，除以七的余数为2。
	 * */
	import java.math.BigInteger;
	import java.util.Scanner;
	
	public class A18_DiuShiDeSanGeShu {
	
		public static void main(String[] args) {
			int arr[] = new int[10001];
			Scanner scanner = new Scanner(System.in);
			for (int i = 0; i < 9997; i++) {
				arr[scanner.nextInt()] = 1;
			}
	
			StringBuffer buffer = new StringBuffer();
			for (int i = 1; i < arr.length; i++) {
				if (arr[i] == 0) {
					buffer.append(i);
				}
			}
	
			BigInteger b = new BigInteger(buffer.toString());
			System.out.println(b.mod(BigInteger.valueOf(7)));
	
			// Long long1 = Long.valueOf(buffer.toString());
			// System.out.println(long1 % 7);
			scanner.close();
	
		}
	}
