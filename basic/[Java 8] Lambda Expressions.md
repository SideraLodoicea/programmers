# Lambda Expressions

- java8 버전부터 지원
- 익명함수를 생성하기 위한 식, 객체지향보다 함수지향에 가깝다
- 함수형 프로그래밍은 병렬처리와 이벤트지향 프로그래밍에 적합하여 딥러닝에서 관심

```java
/*
* 문자열 내 p, y 개수
*/
boolean solution(String s) {
	        boolean answer = true;
	        int p=0; int y=0;
	        
	        for(int n=0; n<s.length(); n++) {
	            char c = s.toLowerCase().charAt(n);
	            if(c =='p') p++; //.equal()은 String 타입만 가능
	            else if(c =='y') y++;
	        }
	        if(p>y || p<y) answer=false;
	        
	        return answer;
	    }

boolean solution2(String s) {
        s = s.toUpperCase();
        return s.chars().filter( e -> 'P'== e).count() == s.chars().filter( e -> 'Y'== e).count();
}
```

```java
class Sample {
	public int sum(int a, int b) {
        return a+b;
    }
    public static void main(String[] args) {
        int a,b;
        Interface sum = (a,b) -> {return a+b;} //매개변수가 2개
        Interface sum = (a,b) -> a+b; //return문만 있는 경우 괄호, return 생략
    }
}
```

```java
Interface a1 = (int a) -> {System.out.println(a);}
Interface a2 = a -> ... // 매개변수 1개
Interface a3 = () -> ... // 매개변수 0개인 경우 빈 소괄호
```

```
public class Ramda_sample {
	@FunctionalInterface
	public interface Number {
		int getMax(int a, int b);
	}
	public static void main(String[] args) {
		Number n = (x,y) -> (x>=y)? x:y;
		System.out.println(n.getMax(10,30));
	}
}
```

```java
// Runnable 인스턴스 생성
Runnable r = () -> {
	for(int i=0; i<10; i++) {
		System.out.println(i);
	}
}
Thread t = new Thread(r);
t.start();

// Thread 호출
Thread t = new Thread( ()-> {
	for(int i=0; i<10; i++) {
		System.out.println(i);
	}
})
```

