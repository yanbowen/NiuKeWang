	package niukewang;
	
	/*
	 * 题目描述:
	 * 
	 * 给定n个整数，请统计出每个整数出现的次数，按出现次数从多到少的顺序输出。
	 * 
	 * 输入描述:
	 * 	输入的第一行包含一个整数n，表示给定数字的个数。
	 * 	第二行包含n个整数，相邻的整数之间用一个空格分隔，表示所给定的整数。
	 * 
	 * 输入
	 * 	12
	 * 	5 2 3 3 1 3 4 2 5 2 3 5
	 * 输出
	 * 	3 4
	 * 	2 3
	 * 	5 3
	 * 	1 1
	 * 	4 1
	 */
	import java.io.BufferedReader;
	import java.io.IOException;
	import java.io.InputStreamReader;
	import java.util.ArrayList;
	import java.util.Collections;
	import java.util.Comparator;
	import java.util.HashMap;
	import java.util.List;
	import java.util.Map;
	
	public class A13_ShuZiPaiXu {
		public static void main(String[] args) throws IOException {
			BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));
	
			int n = Integer.parseInt(reader.readLine());
			String[] strs = reader.readLine().split(" ");
			Map<Integer, Integer> map = new HashMap<Integer, Integer>();
	
			for (int i = 0; i < n; i++) {
	
				if (map.containsKey(Integer.parseInt(strs[i]))) {
					map.put(Integer.parseInt(strs[i]), map.get(Integer.parseInt(strs[i])) + 1);
				} else {
					map.put(Integer.parseInt(strs[i]), 1);
				}
			}
	
			// hashmap按value值遍历
			List<Map.Entry<Integer, Integer>> list_Data = new ArrayList<Map.Entry<Integer, Integer>>(map.entrySet());
			Collections.sort(list_Data, new Comparator<Map.Entry<Integer, Integer>>() {
				public int compare(Map.Entry<Integer, Integer> o1, Map.Entry<Integer, Integer> o2) {
	
					if (o2.getValue().compareTo(o1.getValue()) > 0) {// 按value递减顺序排序
						return 1;
					} else if (o2.getValue().compareTo(o1.getValue()) == 0) {
						if (o2.getKey().compareTo(o1.getKey()) < 0)// 如果value相同输出key小的
							return 1;
						else
							return -1;
					} else {
						return -1;
					}
				}
			});
			// System.out.println(list_Data);//次输出格式为：[3=4, 5=3, 2=3, 4=1, 1=1]
			for (Map.Entry<Integer, Integer> v : list_Data) {
				System.out.println(v.getKey() + " " + v.getValue());
			}
			reader.close();
		}
	
	}
