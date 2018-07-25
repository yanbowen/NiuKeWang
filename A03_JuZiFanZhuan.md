	package niukewang;
	
	/*
	 题目描述
	给定一个句子（只包含字母和空格）， 将句子中的单词位置反转，单词用空格分割,
	单词之间只有一个空格，前后没有空格。 
	比如： （1） “hello xiao mi”-> “mi xiao hello”
	*/
	import java.util.Scanner;
	
	public class A03_JuZiFanZhuan {
	
		public static void main(String[] args) {
			Scanner scanner = new Scanner(System.in);
			String str = scanner.nextLine();
			String arr[] = str.split(" ");
	
			for (int i = arr.length - 1; i > 0; i--) {
	
				System.out.print(arr[i] + " ");
			}
			System.out.print(arr[0]);
			scanner.close();
		}
	}
