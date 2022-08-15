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

# 졸프

#### Socket Client

``` 

package com.example.smartdoorock;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.os.Handler;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import java.io.ObjectInputStream;
import java.io.ObjectOutputStream;
import java.net.Socket;

public class MainActivity extends AppCompatActivity {

    EditText addressInput; 
    EditText dataInput; 

    String str;
    String addr;

    String response; 

    Handler handler = new Handler(); 
    
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        addressInput = findViewById(R.id.addressInput);
        dataInput = findViewById(R.id.dataInput);
        Button socketConnectBtn = findViewById(R.id.socketConnectBtn);
        
        socketConnectBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                addr = addressInput.getText().toString().trim();
                str = dataInput.getText().toString();
                SocketThread thread = new SocketThread(addr, str);
                thread.start();
            }
        });
    }

    class SocketThread extends Thread{

        String host; 
        String data; 

        public SocketThread(String host, String data){
            this.host = host;
            this.data = data;
        }

        @Override
        public void run() {

            try{
                int port = 5555; 
                Socket socket = new Socket(host, port); 
                ObjectOutputStream outstream = new ObjectOutputStream(socket.getOutputStream()); 
                outstream.writeObject(data); 
                outstream.flush(); 

                ObjectInputStream instream = new ObjectInputStream(socket.getInputStream()); 
                response = (String) instream.readObject(); 

              
                handler.post(new Runnable() {
                    @Override
                    public void run() {
                        Toast.makeText(MainActivity.this, "서버 응답 : " + response, Toast.LENGTH_LONG).show();
                    }
                });

                socket.close(); 

            }catch(Exception e){
                e.printStackTrace();
            }
        }
    }
}

```

<br>
# 졸프

#### Socket Server

``` 

import java.io.ObjectInputStream;
import java.io.ObjectOutputStream;
import java.net.InetAddress;
import java.net.ServerSocket;
import java.net.Socket;

public class SocketServer {

    public static void main(String[] args) {
        int portNumber = 5555;

        try {
            System.out.println("서버를 시작합니다...");
            ServerSocket serverSocket = new ServerSocket(portNumber);
            System.out.println("포트 " + portNumber + "에서 요청 대기중...");

            while(true) {
                Socket socket = serverSocket.accept(); 
                InetAddress clientHost = socket.getLocalAddress();
                int clientPort = socket.getPort();
                System.out.println("클라이언트 연결됨. 호스트 : " + clientHost + ", 포트 : " + clientPort);

                ObjectInputStream instream = new ObjectInputStream(socket.getInputStream()); 
                Object obj = instream.readObject(); 
                System.out.println("클라이언트로부터 받은 데이터 : " + obj); 

                ObjectOutputStream outstream = new ObjectOutputStream(socket.getOutputStream()); 
                outstream.writeObject(obj + " from server"); 
                outstream.flush(); 
                socket.close(); 
            }
        }catch(Exception e) {
            e.printStackTrace();
        }
    }
}
```

<br>
