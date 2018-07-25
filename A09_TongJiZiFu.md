	package niukewang;
	
	/*
	题目描述
		给定一个英文字符串,请写一段代码找出这个字符串中首先出现三次的那个英文字符。
	输出描述:
		输出首先出现三次的那个英文字符
	输入
		Have you ever gone shopping and
	输出
		e
	 */
	import java.io.BufferedReader;
	import java.io.IOException;
	import java.io.InputStreamReader;
	import java.util.HashMap;
	
	public class A09_TongJiZiFu {
	
		public static void main(String[] args) throws IOException {
			BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
			char[] cs = br.readLine().toCharArray();
	
			HashMap<Character, Integer> map = new HashMap<>();
	
			for (int i = 0; i < cs.length; i++) {
				if (!(cs[i] >= 'a' && cs[i] <= 'z') && !(cs[i] >= 'A' && cs[i] <= 'Z'))
					continue; // 题目陷阱啊！！输入啥都有，输出只要字母
				map.put(cs[i], map.containsKey(cs[i]) ? map.get(cs[i]) + 1 : 1);
				if (map.get(cs[i]) == 3) {
					System.out.print(cs[i]);
					break;
				}
			}
			br.close();
		}
	}
