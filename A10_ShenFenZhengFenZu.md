	package niukewang;
	
	/*
	题目描述
		用户在输入身份证的过程中经常会输入错误，
		为了方便用户正确输入需要在输入过程中对用户的输入按照 6+8+4 的格式进行分组，
		实现一个方法接收输入过程中的身份证号，返回分组后的字符
	输入
		5021
		502104 198803
		502104198803308324
	输出
		5021
		502104 198803
		502104 19880330 8324
	*/
	import java.io.BufferedReader;
	import java.io.IOException;
	import java.io.InputStreamReader;
	
	public class A10_ShenFenZhengFenZu {
	
		public static void main(String[] args) throws IOException {
			BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
			char arr[] = br.readLine().replace(" ", "").toCharArray();
	
			for (int i = 0; i < arr.length; i++) {
				System.out.print(arr[i]);
				if (i == 5)
					System.out.print(" ");
				if (i == 13)
					System.out.print(" ");
			}
		}
	}
