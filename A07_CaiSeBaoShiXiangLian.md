	package niukewang;
	
	/*
	 * 题目描述:
	 * 
	 * 有一条彩色宝石项链，是由很多种不同的宝石组成的，包括红宝石，蓝宝石，钻石，翡翠，珍珠等。
	 * 有一天国王把项链赏赐给了一个学者，并跟他说，你可以带走这条项链，但是王后很喜欢红宝石，
	 * 蓝宝石，紫水晶，翡翠和钻石这五种，我要你从项链中截取连续的一小段还给我，
	 * 这一段中必须包含所有的这五种宝石，剩下的部分你可以带走。如果无法找到则一个也无法带走。
	 * 请帮助学者找出如何切分项链才能够拿到最多的宝石。
	 * 
	 * 示例1
	 * 输入
	 * ABCYDYE
	 * ATTMBQECPD
	 * 
	 * 输出
	 * 1
	 * 3
	 */
	import java.util.Scanner;
	
	public class A07_CaiSeBaoShiXiangLian {
	
		public static void main(String[] args) {
	
			Scanner scanner = new Scanner(System.in);
			while (scanner.hasNext()) {
				StringBuffer buff = new StringBuffer(scanner.nextLine());
				buff.append(buff);
				char s[] = buff.toString().toCharArray();
				int length = s.length;
	
				int num[] = new int[5];
				for (int i = 0; i < 5; i++)
					num[i] = 0;
	
				int min = length / 2;
				for (int i = 0; i <= length / 2 - 1; i++) {
					int count = 0;
					if (s[i] >= 'F')
						continue;
					else {
						for (int j = i; j <= length / 2 + i - 1; j++) {
							int temp = (int) (s[j] - 'A');
							if (temp < 5 && num[temp] == 0) {
								num[temp]++;
								count++;
							}
							if (count == 5) {
								min = Math.min(min, j - i + 1);
								for (int k = 0; k < 5; k++)
									num[k] = 0;
								break;
							}
						}
					}
				}
				System.out.println(length / 2 - min);
			}
			scanner.close();
		}
	}
