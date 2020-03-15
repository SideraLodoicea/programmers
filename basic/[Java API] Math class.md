# Math Class

* java.lang.Math
* Oracle docs <https://docs.oracle.com/javase/8/docs/api/java/lang/Math.html>
* 수학에서 자주 사용하는 상수들, 함수들을 미리 구현해놓은 클래스
* Math 클래스의 모든 메소드는 static method 이므로 객체를 생성하지 않고도 바로 사용



* Field

  E 
  public static final double E
  오일러의 수, 자연로그의 밑(base) 
  ≒ 2.718

  
  
  PI 
  public static final double PI
원주율 
  ≒ 3.141592



* Method

  static double random() 0.0 이상 1.0 미만의 난수 생성

  static double abs(double a) absolute

  static int round(float a) 소수점 첫째 자리 반올림

  static double floor(double a) 소수 부분 버림 

  static double floorMod(int x, int y)

  static double ceil(double a)  소수 부분 올림

  static double max(double a, double b)

  static double min(double a, double b)

  static double pow(double a, double b) a의 b승

  static double toRaidans(double angdeg) 육십분법의 각도 값을 대략적인 호도법의 라디안 값으로 변환

```java
(int)(Math.random()*100);	//0~99
(int)(Math.random()*6);		//0~5
((int)(Math.randon()*6)+1);	//1~6

floorMod(+4, -3) == -2;   and (+4 % -3) == +1
floorMod(-4, +3) == +2;   and (-4 % +3) == -1
floorMod(-4, -3) == -1;   and (-4 % -3) == -1
```

```java
/*
* programmers 두 정수 사이의 합
* 등차수열의 합 공식
* - 등차수열의 제1항부터 제n항까지의 합 S
* - S = n * (제1항+제n항) / 2
*/
class Solution1 {
    public long solution(int a, int b) {
        return sumAtoB(Math.min(a, b), Math.max(b, a));
    }

    private long sumAtoB(long a, long b) {
        return (b - a + 1) * (a + b) / 2;
    }
}

class Solution2 {
  public long solution(int a, int b) {
      long answer = 0;

        int start = Math.min(a, b);
        int end = Math.max(a, b);

        for (int i = start; i <= end; i++) {
            answer += i;
        }
        return answer;
  }
}
```

