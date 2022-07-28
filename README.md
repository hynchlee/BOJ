# BOJ

#### A + B

``` 1000
import java.util.*;

public class Main {

	public static void main(String[] args) {
		
		Scanner scan = new Scanner(System.in);
		
		int A = scan.nextInt();
		int B = scan.nextInt();
		
		System.out.println(A+B);
	}

}
```

<br>

#### A - B

``` 1001
import java.util.*;

public class Main {

	public static void main(String[] args) {
		
		Scanner scan = new Scanner(System.in);
		
		int A = scan.nextInt();
		int B = scan.nextInt();
		
		System.out.println(A-B);
	}

}
```
<br>

#### A / B

``` 1008
import java.util.*;

public class Main {

	public static void main(String[] args) {
		
		Scanner scan = new Scanner(System.in);
		
		int A = scan.nextInt();
		int B = scan.nextInt();
		
		System.out.println(A8B);
	}

}

```

#### A / B

``` 1008

import java.util.*;

public class Main {

	public static void main(String[] args) {
		
		Scanner scan = new Scanner(System.in);
		
		double A = scan.nextDouble();
		double B = scan.nextDouble();
		
		System.out.println(A/B);
	}

}

```
<br>

#### 모음의 개수

``` 1264

package Tutorial;
import java.util.*;

public class Main {

	public static void main(String[] args) {
		
		Scanner scan = new Scanner(System.in);
		
		while (true) {
			String str = scan.nextLine();
			
			if(str.equals("#")) {
				break;
			}
			char[] index = {'A','E','I','O','U','a','e','i','o','u'};
			int count = 0;
			
			for(int i =0; i<str.length(); i++) {
				char c = str.charAt(i);
				for(int j = 0; j<index.length; j++) {
					if(c==index[j]) {
						count++;
					}
				}
			}
			System.out.println(count);

		}
	}

}

```
<br>
