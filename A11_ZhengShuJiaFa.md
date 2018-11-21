	package niukewang;
	
	/*
	 * 题目描述:
	 * 
	 * 请设计一个算法能够完成两个用字符串存储的整数进行相加操作，对非法的输入则返回error
	 * 
	 * 输入描述:
	 * 	输入为一行，包含两个字符串，字符串的长度在[1,100]。
	 * 
	 * 输入
	 * 	123 123
	 * 	abd 123
	 * 输出
	 * 	246
	 * 	error
	 */
	import java.math.BigInteger;
	import java.util.Scanner;
	
	public class A11_ZhengShuJiaFa {
		public static void main(String[] args) {
			Scanner scanner = new Scanner(System.in);
			BigInteger bi1 = null;
			BigInteger bi2 = null;
			try {
				bi1 = scanner.nextBigInteger();
				bi2 = scanner.nextBigInteger();
			} catch (Exception e) {
				System.out.println("Error");
				return;
			}
	
			System.out.println("加法操作：" + bi2.add(bi1)); // 加法操作
			scanner.close();
		}
	}
