	package niukewang;
	
	import java.util.Arrays;
	import java.util.Collections;
	import java.util.Comparator;
	import java.util.HashMap;
	import java.util.LinkedList;
	import java.util.List;
	import java.util.Map;
	import java.util.Scanner;
	
	public class A28_monkeys_eat_peaches {
		public static void main(String[] args) {
			Scanner sc = new Scanner(System.in);
			HashMap<Integer, Integer> map = new HashMap<Integer, Integer>();
			int n = sc.nextInt();
			int m = sc.nextInt();
			int[] peach = new int[m];
			int[] monkey = new int[n];
			for (int i = 0; i < m; i++) {
				peach[i] = sc.nextInt();
			}
			for (int i = 0; i < n; i++) {
				int zdl = sc.nextInt();
				int je = sc.nextInt();
				monkey[i] = zdl;
				map.put(zdl, je);
			}
			List<Map.Entry<Integer, Integer>> list = new LinkedList<Map.Entry<Integer, Integer>>(map.entrySet());
			Collections.sort(list, new Comparator<Map.Entry<Integer, Integer>>() {
				public int compare(Map.Entry<Integer, Integer> map1, Map.Entry<Integer, Integer> map2) {
					return (map2.getKey() - map1.getKey() == 0) ? (map1.getKey() - map2.getKey())
							: (map2.getKey() - map1.getKey());
				}
			});
			for (int i = 0; i < list.size(); i++) {
				int flag = list.get(i).getValue();
				Arrays.sort(peach);
				for (int j = m - 1; j >= 0; j--) {
					if (flag >= peach[j]) {
						flag -= peach[j];
						peach[j] = 0;
					} else {
						continue;
					}
				}
				map.put(list.get(i).getKey(), flag);
			}
	
			for (int i = 0; i < n; i++) {
				System.out.println(map.get(monkey[i]));
			}
	
		}
	}
