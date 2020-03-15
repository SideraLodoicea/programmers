# 문자열 내 마음대로 정렬하기

```java
Class solution {
	 public String[] solution1(String[] strings, int n) {
		for(int i=0; i<strings.length; i++) 
			strings[i]= Character.toString(strings[i].charAt(n)).concat(strings[i]);
		
		Arrays.sort(strings);
		
		for(int i=0; i<strings.length; i++) 
			strings[i]= strings[i].substring(1);
	    return strings;
	}
}
```

* 야매 재질이긴해도 가성비 지림

```java
Class solution {
	public String[] solution1(String[] strings, int n) {
		for(int i=1; i<strings.length; i++) {
			for(int j=0; j<strings.length-i; j++) {
				if(Character.toString(strings[j].charAt(n))
						.compareTo(Character.toString(strings[j+1].charAt(n)))>0) {
				// System.out.println(Character.toString(strings[j].charAt(n)));
					String tmp = strings[j];
					strings[j] = strings[j+1];
					strings[j+1]=tmp;
				} else {
					if(strings[j].compareTo(strings[j+1])>0) {
						String tmp = strings[j];
						strings[j] = strings[j+1];
						strings[j+1]=tmp;
                        ...
```

* charAt 메소드로 어케 해보고 싶은데 잘 모르겠다 + 최악의 경우 O(n^2) ...

```java
class Solution {
  public String[] solution(String[] strings, int n) {
      Arrays.sort(strings, new Comparator<String>(){
          @Override
          public int compare(String s1, String s2){
              if(s1.charAt(n) > s2.charAt(n)) return 1;
              else if(s1.charAt(n) == s2.charAt(n)) return s1.compareTo(s2);
              else if(s1.charAt(n) < s2.charAt(n)) return -1;
              else return 0;
          }
      });
      return strings;
  }
}
```

* 다른 사람 답