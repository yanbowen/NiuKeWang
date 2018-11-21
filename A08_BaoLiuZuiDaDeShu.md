	package niukewang;
	
	/*
	 * String str1 = "abcdefg";   
	 * char ch1 = str1.charAt(0); 
	 * codePointAt返回指定索引处的字符（Unicode代码点） : a的Unicode码为:97
	 * 
	 * 题目描述:
	 * 
	 * 给定一个十进制的正整数number，选择从里面去掉一部分数字，希望保留下来的数字组成的正整数最大。
	 * 
	 * 输入
	 * 		325 1
	 * 输出
	 * 		35
	 */
	import java.util.Scanner;
	
	public class A08_BaoLiuZuiDaDeShu {
	
		public static void main(String[] args) {
			Scanner scanner = new Scanner(System.in);
			while (scanner.hasNext()) {
				StringBuilder sb = new StringBuilder();
				sb.append(scanner.next());
	
				int cnt = scanner.nextInt();
				int count = 0;
	
				while (count < cnt) {
					int len = sb.length() - 1;
					int flag = 0;
					while (flag < len && sb.codePointAt(flag) >= sb.codePointAt(flag + 1))
						flag++;
					sb.deleteCharAt(flag);
					count++; // 记录删除个数
				}
				System.out.println(sb);
			}
			scanner.close();
		}
	}
