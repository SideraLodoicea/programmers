# Arrays Class

* java.util.Arrays
* java.lang 패키지와 달리 import로 패키지를 불러와야 사용 가능
* Oracle docs <https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Array.html>
* Arrays 클래스의 모든 메소드는 static method 이므로 객체를 생성하지 않고도 바로 사용



* Method

  static  <T> List <T>  asList(T... a)

  static int binarySearch(double[] a, double key) 이진 검색으로 key의 인덱스 반환

  static double[] copyOf(double[] original, int newLength) 

  static double[] copyOfRange(double[] original, int from, int to) from 부터 to-1 까지

  static boolean equals(double[] a, double[] a2)

  static void fill(double[] a, double val)

  static void sort(double[] a)

  static IntStream stream(int[] a)

  static String toString(double[] a)

  ```java
  import java.util.Arrays;
  
  String[] part = {"A","B","C"};
  if(Array.asList(stringArray).contains(inputText)) ...
  
  int[] arr1 = {1, 2, 3, 4, 5};
  int[] arr2 = Arrays.copyOf(arr1, 3); 	// {1,2,3}
  int[] arr3 = Arrays.copyOf(arr1, 10); 	// {1,2,3,4,5,0,0,0,0,0}
  
  Arrays.sort(arr, 1, arr.length) // 0번째 item을 제외한 1번부터 끝까지 정렬
  Arrays.sort(arr, Collections.reverseOrder()); // 내림차순 정렬
  
  Arrays.stream(stringArray).forEach(System.out::println);
  
  double[] values = {1.0, 1.1, 1.2};
  System.out.println(values.toString()); 	// [D@46a49e6 
  System.out.println(Arrays.toString(values)); // [1.0, 1.1, 1.2] 
  ```

  ```java
  /*
  * programmers K번째 수
  * example : [1, 5, 2, 6, 3, 7, 4]를 2번째부터 5번째까지 자른 후 정렬합니다. 
  */
  import java.util.Arrays;
  
  class Solution {
      public int[] solution(int[] array, int[][] commands) {
          int[] answer = new int[commands.length];
          int anCnt = 0;
          for (int[] a : commands) {
              int[] tmp = Arrays.copyOfRange(array, a[0]-1, a[1]);
              Arrays.sort(tmp);
  
              answer[anCnt++] = tmp[a[2]-1];
          }
          return answer;
      }
  }
  ```

  

