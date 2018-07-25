	package niukewang;
	
	/*
	题目描述
		给你两个集合，要求{A} + {B}。 注：同一个集合中不会有两个相同的元素。
	输入
		3 3
		1 3 5
		2 4 6
	输出
		1 2 3 4 5 6
	*/
	import java.io.BufferedReader;
	import java.io.IOException;
	import java.io.InputStreamReader;
	import java.util.Iterator;
	import java.util.TreeSet;
	
	public class A12_JiHe {
		public static void main(String[] args) throws IOException {
			BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));
	
			// 读取第一行的数据
			String[] numberArr = reader.readLine().split(" ");
			int numberA = Integer.parseInt(numberArr[0]);// 表示A行的集合的长度
			int numberB = Integer.parseInt(numberArr[1]); // 表示B行的集合的长度
	
			String[] aArr = reader.readLine().split(" "); // 读取到A行的数据
			String[] bArr = reader.readLine().split(" "); // 读取到B行的数据
	
			// 不重复集合
			TreeSet<Integer> set = new TreeSet<>();
	
			// //自定义反向排序
			// TreeSet<Integer> set = new TreeSet<>(new Comparator<Integer>() {
			//
			// @Override
			// public int compare(Integer o1, Integer o2) {
			// if (o2.compareTo(o1) > 0) {// 按value递减顺序排序
			// return 1;
			// } else {
			// return -1;
			// }
			// }
			//
			// });
			for (int i = 0; i < aArr.length; i++) {
				set.add(Integer.parseInt(aArr[i]));
			}
			for (int i = 0; i < bArr.length; i++) {
				set.add(Integer.parseInt(bArr[i]));
			}
	
			StringBuffer buffer = new StringBuffer();
			Iterator<Integer> iterator = set.iterator();
			while (iterator.hasNext()) {
				buffer.append(iterator.next());
				buffer.append(" ");
			}
			// 去掉最后的一个空格
			buffer.delete(buffer.length() - 1, buffer.length());
			System.out.println(buffer.toString());
		}
	
	}
