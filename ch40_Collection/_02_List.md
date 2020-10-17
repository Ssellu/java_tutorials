# java.util.List
## 1. List 의 특징
List의 특징은 다음과 같습니다.   
><pre>선형 구조<br>인덱스 있음<br>중복 원소 저장 가능</pre>
List 계열의 클래스들은 선형으로 원소를 저장합니다. Array 라는 단어가 들어간 클래스는 원소를 저장할 때 배열을 사용하고,<br>Linked 가 들어가는 클래스들은 연결리스트를 사용합니다. <br>
중복되는 원소가 저장되어도 인덱스로 구분이 가능하기 때문에 중복 저장을 허용합니다.

## 2. List 의 주요 메서드 
List 의 주요 메서드를 살펴봅시다. List 계열의 모든 클래스는 List 인터페이스의 추상 메서드를 구현했기때문에 각 클래스의 고유 멤버를 제외한 나머지 핵심 기능은 사용방법이 모두 동일합니다.   

> API Docs : [https://docs.oracle.com/javase/8/docs/api/java/util/List.html](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)
### 원소 추가
```java
boolean	add(E e)
```
원소 e를 마지막 위치에 **추가**합니다. (여기서 E는 제네릭입니다. 제네릭 지정이 없다면 Object 형으로 지정됩니다.)
<br><br><br>
```java
void	add(int index, E e)
```
원소 e를 index 번 위치에 **삽입**합니다.
<br><br><br>
```java
boolean	addAll(Collection<? extends E> c)
```
다른 컬렉션 객체의 모든 원소를 **한꺼번에 추가**합니다. 리스트에 변화가 생긴 경우 (즉, 정상적으로 추가된 경우) true를 return합니다.
<br><br><br>
```java
boolean	addAll(int index, Collection<? extends E> c)
```
다른 컬렉션 객체의 모든 원소를 index 번 위치에 순서대로 **한꺼번에 삽입**합니다. 리스트에 변화가 생긴 경우 true를 return합니다.
### 원소 삭제
```java
void	clear()
```
Removes all of the elements from this list (optional operation).

```java
boolean	contains(Object o)
```
Returns true if this list contains the specified element.
------------------
```java
boolean	containsAll(Collection<?> c)
```
Returns true if this list contains all of the elements of the specified collection.
------------------
```java
boolean	equals(Object o)
```
Compares the specified object with this list for equality.
------------------
```java
E	get(int index)
```
Returns the element at the specified position in this list.
------------------
```java
int	hashCode()
```
Returns the hash code value for this list.
------------------
```java
int	indexOf(Object o)```
Returns the index of the first occurrence of the specified element in this list, or -1 if this list does not contain the element.
------------------
```java
boolean	isEmpty()```
Returns true if this list contains no elements.
------------------
```java
Iterator<E>	iterator()
```
Returns an iterator over the elements in this list in proper sequence.
------------------
```java
int	lastIndexOf(Object o)
```
Returns the index of the last occurrence of the specified element in this list, or -1 if this list does not contain the element.
------------------
```java
ListIterator<E>	listIterator()
```
Returns a list iterator over the elements in this list (in proper sequence).
------------------
```java
ListIterator<E>	listIterator(int index)
```
Returns a list iterator over the elements in this list (in proper sequence), starting at the specified position in the list.
------------------
```java
E	remove(int index)
```
Removes the element at the specified position in this list (optional operation).
------------------
```java
boolean	remove(Object o)
```
Removes the first occurrence of the specified element from this list, if it is present (optional operation).
------------------
```java
boolean	removeAll(Collection<?> c)
```
Removes from this list all of its elements that are contained in the specified collection (optional operation).
------------------
```java
default void	replaceAll(UnaryOperator<E> operator)
```
Replaces each element of this list with the result of applying the operator to that element.
------------------
```java
boolean	retainAll(Collection<?> c)
```

Retains only the elements in this list that are contained in the specified collection (optional operation).
------------------
```java
E	set(int index, E element)
```
Replaces the element at the specified position in this list with the specified element (optional operation).
------------------
```java
int	size()
```
Returns the number of elements in this list.
------------------
```java
default void	sort(Comparator<? super E> c)
```
Sorts this list according to the order induced by the specified Comparator.
------------------
```java
default Spliterator<E>	spliterator()
```
Creates a Spliterator over the elements in this list.
------------------
```java
List<E>	subList(int fromIndex, int toIndex)
```
Returns a view of the portion of this list between the specified fromIndex, inclusive, and toIndex, exclusive.
------------------
```java
Object[]	toArray()
```
Returns an array containing all of the elements in this list in proper sequence (from first to last element).
------------------
```java
<T> T[]	toArray(T[] a)
```
Returns an array containing all of the elements in this list in proper sequence (from first to last element); the runtime type of the returned array is that of the specified array.

