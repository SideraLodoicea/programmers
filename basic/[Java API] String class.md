# String class

* java.lang.String

* Oracle Docs <https://docs.oracle.com/javase/9/docs/api/java/lang/String.html>

* String 인스턴스는 한 번 생성되면 그 값을 읽기만 할 수 있고, 변경할 수는 없습니다. 불변 객체(immutable object)라고 합니다.

  즉, 자바에서 덧셈(+) 연산자를 이용하여 문자열 결합을 수행하면, 기존 문자열의 내용이 변경되는 것이 아니라 내용이 합쳐진 새로운 String 인스턴스가 생성되는 것입니다.

  (<http://tcpschool.com/java/java_api_string>)



* Method

  char charAt(int index) 0부터 시작

  IntStream chars() java9부터 지원

  ```java
  /* java7 */
  for(int i =0; i<str.length(); i++)
  	System.out.println(str.charAt(i));
  	
  /* java9 */
  str.chars().forEach(i -> System.out.println((char)i));
  ```

  boolean contains(CharSequence s)

  boolean equals(Object o)

  boolean isEmpth()

  int length()

  int compareTo(String str) 대소문자 구분하여 비교, 같으면 0 반환

  int indexOf(int ch) 0부터 시작, ch가 몇 번째에 있는지 반환, 없으면 -1

  String replace(char oldChar, char newChar)

  String replace(String reg, String repla)

  String substring(int beginID)

  String substring(int beginID, int endID) b부터 e-1까지 반환

  String toLowerCase()

  String toUpperCase()

  String toString()

  String concat(String str)

  String[] split(String regular)

  String[] split(String reg, int limit)

  String trim() 모든 공백문자(띄어쓰기, 탭) 제거

  ```java
  /*
  * programmers 가운데 글자 가져오기
  * 문자열의 길이가 짝수일 때 가운데 두 글자, 홀수일 때 가운데 한 글자를 가져온다.
  */
  class StringExercise{
      String getMiddle(String word){
          return word.substring((word.length()-1) / 2, word.length()/2 + 1);
      }
      public static void  main(String[] args){
          StringExercise se = new StringExercise();
          System.out.println(se.getMiddle("power"));
      }
  }
  ```

  