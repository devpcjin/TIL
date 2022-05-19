# Generics
## Generics
### Generics 란?
- 다양한 타입의 객체들을 다루는 `method`나 `collection class` 컴파일 시의 type를 체크 해주는 기능

### 사용하는 이유
- 안전성이 높아짐
    - 의도하지 않은 타입의 객체가 저장되는 것을 막고 잘못된 형변환을 막을 수 있기 때문

### Generics 형식과 약어
- 형식
    ```java
        public class 클래스명<T> {...}
        public interface 인터페이스명<T> {...}
    ```
- 타입인자 약어
    ```java
        - <T> == Type
        - <E> == Element
        - <K> == Key
        - <V> == Value
        - <N> == Number
        - <R> == Result
    ```

### 예제
- part of `Collection.java`
    ```java
        public interface Collection<E> extends Iterable<E> {
            int size();
            boolean isEmpty();
            Iterator<E> iterator();
            boolean add(E e);
            <T> T[] toArray(T[] a);
            boolean containsAll(Collection<?> c);
            boolean addAll(Collection<? extends E> c);
        }
    ```

- part of `List.java`
    ```java
        public interface List<E> extends Collection<E> {
        // Collection 에 있는 메소드들 모두 포함 
        // + List 에만 있는 메소드들
            boolean add(E e);
        }
    ```

- part of `ArrayList.java`
    ```java
        public class ArrayList<E> extends AbstractList<E>
                implements List<E>, RandomAccess, Cloneable, java.io.Serializable 
        {
            public <T> T[] toArray(T[] a) {
                if (a.length < size)
                    // Make a new array of a's runtime type, but my contents:
                    return (T[]) Arrays.copyOf(elementData, size, a.getClass());
                System.arraycopy(elementData, 0, a, 0, size);
                if (a.length > size)
                    a[size] = null;
                return a;
            }
            public E get(int index) {
                rangeCheck(index);

                return elementData(index);
            }
            public boolean add(E e) {
                ensureCapacityInternal(size + 1);  // Increments modCount!!
                elementData[size++] = e;
                return true;
            }
        }
    ```