# ArrayList Class

* java.util.ArrayList
* Oracle docs <https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html>



* Method

  boolean add(E e) 삽입

  boolean add(int index, E element) 해당 인덱스에 객체를 삽입

  boolean addAll(Collection c)

  E remove(int index)

  boolean remove(Object o)

  boolean removeAll(Collection<?> c)

  boolean removeIf(Predicate filter)

  E get(int index)

  E set(int index, E e)

  

  boolean isEmpty()

  void clone()

  void clear()  모두 null로 초기화, size 0

  int size()

  int indexOf(Object o)

  boolean contains(Object o)

  void sort(Comparator c)

  Object[] toArray(T[] a)

  void forEach(COnsumer action)

  Iterator<E> iterator()

```java
/*
* ArrayList를 배열로 변환
*/
ArrayList<Integer> answer = new ArrayList<>(); // 선언
int[] ret = new int[answer.size()];
for (int i=0; i<ret.length; i++) 
     ret[i] = answer.get(i).intValue();
```

```java
/*
* programmers 같은 숫자는 싫어
*/
public class Solution {
    public int[] solution(int []arr) {
        ArrayList<Integer> answer = new ArrayList<>();

        answer.add(arr[0]);
        for(int i=1; i<arr.length; i++) {
            if(arr[i]!=arr[i-1]) {
                answer.add(arr[i]);
            }
        }

        int[] ret = new int[answer.size()];
        for (int i=0; i<ret.length; i++) {
            ret[i] = answer.get(i).intValue();
        }
        return ret;
    }
}
```

