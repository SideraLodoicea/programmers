# Map Collection Class

1. HashTable<K, V>
2. HashMap<K, V>
   - (key, value) 를 묶어서 하나의 데이터(매핑, 엔트리)로 저장
   - key와 value값에 null을 허용한다
   - key는 중복을 허용하지 않고 value의 중복은 허용한다
   - 중복된 key값을 저장하면 기존의 값이 없어지고 마지막에 저장된 값이 남는다
   - 엔트리의 저장 순서를 유지하지 않는다
   - 저장은 느리지만 많은 양의 데이터를 빠르게 검색
3. TreeMap<K, V>
   * 비교적 저장이 빠르고 데이터를 느린 속도로 가져옴



- Map interface

  - Method

    boolean containsKey(Object k) k와 일치하는 Map의 key가 있는지

    boolean containsValue(Object v) v와 일치하는 Map의 value가 있는지

    boolean equals(Obj o) 동일한 Map인지 비교

    boolean isEmpty() Map이 비었는지 확인

    void putAll(Map m) m의 모든 (key, value)를 추가

    void clear() Map의 모든 객체를 삭제

    Object remove(Obj key) k와 일치하는 (key, value)를 삭제

    Object get(Obj key) k와 대응하는 value를 찾아서 반환

    Object put(Obj k, Obj v)Map에 (k,v)를 저장

    Set entrySet() Map에 저장된 (key,value)를 Map.Entry타입의 객체로 저장한 Set으로 반환

    Set keySet() Map에 저장된 모든 key로 만들어진 Set 객체를 반환

    int size() Map에 저장된 매핑의 총 개수를 반환

* Map.Entry interface
  * Map interface의 내부 인터페이스

  * Map인터페이스를 구현하는 클래스는 Map.Entry인터페이스도 함께 구현해야한다

  * Method

    boolean equls(Obj o)  동일한 Entry인지 비교 

    Object geKey()  Entry의 key 객체를 반환 

    Object getValue()  Entry의 value 객체를 반환  

    Object setValue(Obj v)  Entry의 value 객체를 지정된 객체로 바꾼다

```java
/*
* programmers 완주하지 못한 선수
*/
public String solution1(String[] participant, String[] completion) {
	String answer="";
    int value =0;
    
    HashMap<String, Integer> hmap = new HashMap<>();
    for(String p: participant) {
        /* if(hmap.get(p)==null) hm.put(p, 1);
        else {
            value=hmap.get(p)+1;
            hmap.put(p, value);
		}*/
        hmap.put(p, hmap.getOrDefault(p,0)+1);
        
    }
    for(String c: completion) {
        value=hmap.get(c)-1;
        hmap.put(c, value);
    }    
    for(String key: hmap.keySet()) 
        if(hmap.get(key)==1) answer=key;
    
    return answer;    
}

public String solution2(String[] participant, String[] completion) {
	Arrays.sort(participant);
    Arrays.sort(completion);
    
    int i;
    for(i=0; i<completion.length; i++)
        if(!participant[i].equals(completion[i]))
            return participant[i];
    
    return participant[i];
}
```

- keySet하고 또 get하는 건 매우 비효율적, get할 때마다 계속 HashMap을 search하니까요. key, value를 같이 가져올 때는 항상 entrySet을 사용해야 해요.
- getOrDefault를 넣어주지 않으면 중복 체크가 되지 않아요. HashMap의 put은 key가 존재하면 value를 새로운 값으로 바꿔주니까요. 이미 등록된 동명이인이 있다면 hm.getOrDefault로 인해서 2라는 값이 들어가겠네요
- 시간 복잡도 O(n)