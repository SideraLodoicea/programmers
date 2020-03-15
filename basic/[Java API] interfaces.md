- spliterator interface

  <https://www.geeksforgeeks.org/java-util-interface-spliterator-java8/>

- Stream interface

  <http://iloveulhj.github.io/posts/java/java-stream-api.html>

  <https://cornswrold.tistory.com/294?category=755361>

  ```java
  List<String> names = Arrays.asList("강성현", "강성현", "깡냉", "강냉", "깡냉");
  
  names.stream()
              .distinct() // 중복 제거
              .forEach(System.out::println);
  System.out.println();
  
  names.stream()
              .filter(n -> n.startsWith("강")) // 필터링
              .forEach(System.out::println);
  System.out.println();
          
  names.stream()
              .distinct()
              .filter(n -> n.startsWith("강")) // 중복 제거 후 필터링
              .forEach(System.out::println);
  ```

  

  ```java
  /*
  * programmers 나누어 떨어지는 숫자 배열
  */
  public int[] solution(int[] arr, int divisor) {
  		ArrayList<Integer> a = new ArrayList<>();
  
  		for(int i: arr) 
  			if (i%divisor == 0) 
  				a.add(i);
                  
  		if(a.size()==0) a.add(-1);
  		int[] answer = new int[a.size()];
  		for(int i=0; i<answer.length; i++) {
  			answer[i]=a.get(i);
  		}
          Arrays.sort(answer);
  		return answer;
  	}
  
  public int solution2(int[] arr, int divisor) {
  		return Arrays.stream(arr).filter(i -> i%divisor ==0).toArray();
  }
  ```

  





