	package niukewang;
	
	/*
	 * 小牛牛为了向他的父母表现他已经长大独立了,他决定搬出去自己居住一段时间。
	 * 一个人生活增加了许多花费: 牛牛每天必须吃一个水果并且需要每天支付x元的房屋租金。
	 * 当前牛牛手中已经有f个水果和d元钱,牛牛也能去商店购买一些水果,商店每个水果售卖p元。
	 * 牛牛为了表现他独立生活的能力,希望能独立生活的时间越长越好,牛牛希望你来帮他计算一下他最多能独立生活多少天。
	 * 
	 * 输入描述:
	 * 		输入包括一行,四个整数x, f, d, p(1 <= x,f,d,p <= 2 * 10^9),以空格分割	3 5 100 10
	 * 
	 * 输出描述:
	 * 		输出一个整数, 表示牛牛最多能独立生活多少天。	11
	 * */
	import java.io.IOException;
	import java.math.BigInteger;
	import java.util.Scanner;
	
	public class A23_MoNi_One {
		public static void main(String[] args) throws IOException {
	
			Scanner scanner = new Scanner(System.in);
			BigInteger x, f, d, p;
			x = scanner.nextBigInteger();
			f = scanner.nextBigInteger();
			d = scanner.nextBigInteger();
			p = scanner.nextBigInteger();
	
			BigInteger[] bis = d.divideAndRemainder(x);
	
			if (bis[0].compareTo(f) < 0) {
				System.out.println(bis[0]);
			} else {
	
				System.out.println(((d.subtract(f.multiply(x))).divideAndRemainder(p.add(x))[0]).add(f));
			}
	
			scanner.close();
		}
	
	}
