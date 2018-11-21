	package niukewang;
	
	/*
	 * 题目描述:
	 * 
	 * 输入两个字符串，从第一字符串中删除第二个字符串中所有的字符。
	 * 例如，输入”They are students.”和”aeiou”，则删除之后的第一个字符串变成”Thy r stdnts.”
	 * 
	 * 输入
	 * 	They are students.
	 * 	aeiou
	 * 输出
	 * 	Thy r stdnts.
	 */
	import java.io.BufferedReader;
	import java.io.IOException;
	import java.io.InputStreamReader;
	
	public class A14_ShanChuGongGongZiFu {
		public static void main(String[] args) throws IOException {
	
			BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
	
			String str = br.readLine().toString();
			String keywords = br.readLine().toString();
			StringBuilder stringBuilder = new StringBuilder();
	
			char[] cs = str.toCharArray();
	
			for (int i = 0; i < cs.length; i++) {
	
				if (keywords.indexOf(cs[i]) == -1)
					stringBuilder.append(cs[i]);
			}
	
			System.out.println(stringBuilder.toString());
			br.close();
		}
	}
