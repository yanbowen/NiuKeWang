	package niukewang;
	
	import java.util.Random;
	
	/*
	 *获取6位随机生成的验证码
	 * */
	
	public class A25_YanZhengMa {
		public static void main(String[] args) {
			String res = A25_YanZhengMa.getVerifyCode();
			System.out.println(res);
		}
	
		public static String getVerifyCode() {
			String[] verifyString = new String[] { "0", "1", "2", "3", "4", "5", "6", "7", "8", "9" , "a", "b", "c", "d", "e", "f", "g", "h", "i"
					, "j", "k", "l", "m", "n", "o", "p", "q", "r", "s", "t", "u", "v", "w", "x", "y", "z"};
			Random random = new Random(System.currentTimeMillis());
			StringBuilder verifyBuilder = new StringBuilder();
			for (int i = 0; i < 4; i++) {
				int rd = random.nextInt(36);
				verifyBuilder.append(verifyString[rd]);
			}
			String verifyCode = verifyBuilder.toString();
			return verifyCode;
		}
	}
