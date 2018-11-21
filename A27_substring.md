	package niukewang;
	
	import java.util.Scanner;
	
	/*
	 * 题目描述: 
	 * 
	 * public String substring(int beginIndex, int endIndex)
	 * 第一个int为开始的索引，对应String数字中的开始位置， 第二个是截止的索引位置，对应String中的结束位置
	 * 1、取得的字符串长度为：endIndex - beginIndex;
	 * 2、从beginIndex开始取，到endIndex结束，从0开始数，其中不包括endIndex位置的字符 
	 * 如： 
	 * "hamburger".substring(4, 8) 
	 * 		returns "urge"
	 *  
	 * "smiles".substring(1, 5)
	 * 		returns "mile"
	 * 取长度大于等于3的字符串a的后三个子字符串，只需a.subString(a.length()-3,a.length());
	 */
	public class A27_substring {
		public static void main(String[] args) {
			Scanner sc = new Scanner(System.in);
			String s1 = sc.nextLine();
			String s2 = sc.nextLine();
			String str2[] = s2.split("");
			String result = "Yes";
	
			for (int i = 0; i < str2.length; i++) {
				int num = s1.indexOf(str2[i]);
				if (num != -1) {
					s1 = s1.substring(num + 1);
				} else {
					result = "No";
					break;
				}
			}
			System.out.println(result);
		}
	
		private static void mySubstring() {
			Scanner sc = new Scanner(System.in);
			String s1 = sc.nextLine();
			String s2 = sc.nextLine();
			String str1[] = s1.split("");
			String str2[] = s2.split("");
	
			for (int i = 0; i < str2.length; i++) {
				for (int j = 0; j < str1.length; j++) {
					if (str1[j].equals(str2[i])) {
						str1[j] = " ";
						str2[i] = " ";
						break;
					}
				}
			}
	
			for (int i = 0; i < str2.length; i++) {
				if (str2[i] != " ") {
					System.out.println("No");
					return;
				}
			}
			System.out.println("Yes");
		}
	}
