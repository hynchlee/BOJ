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

#### 약수

``` 1037

import java.util.Arrays;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt(); // 약수의 개수
        int[] num = new int[N];

        for(int i=0; i<N; i++){
            num[i] = sc.nextInt();
        }
        Arrays.sort(num);
        System.out.println((num[0])*(num[N-1]));
    }
}

```

<br>

#### 나누기

``` 1075(다시 풀기)

import java.util.*;

public class Main {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int N = sc.nextInt();
		int F = sc.nextInt();
		N = (N/100) * 100; 
		
		while(N%F != 0)
			N++;
		
		N %= 100;
		
		if(N < 10) System.out.println("0" + N);
		else System.out.println(N);
	}
}

```

<br>

#### 별찍기-4

``` 2441

import java.util.*;
 
public class Main {
    public static void main(String[] args){
        
        Scanner scan = new Scanner(System.in);
        
        int num = scan.nextInt();
        
        for(int i=0; i<num; i++) { 
            
            for(int j=i+1; j<=num; j++) {
            
                System.out.print("*");
            }        
            System.out.println();            
        }
    }
}

```

<br>
