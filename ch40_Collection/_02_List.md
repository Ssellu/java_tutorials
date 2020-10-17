# java.util.List
## 1. List 의 특징
List의 특징은 다음과 같습니다.   
><pre>선형 구조<br>인덱스 있음<br>중복 원소 저장 가능</pre>
List 계열의 클래스들은 선형으로 원소를 저장합니다. Array 라는 단어가 들어간 클래스는 원소를 저장할 때 배열을 사용하고,<br>Linked 가 들어가는 클래스들은 연결리스트를 사용합니다. <br>
중복되는 원소가 저장되어도 인덱스로 구분이 가능하기 때문에 중복 저장을 허용합니다.

## 2. List 의 주요 메서드 
List 의 주요 메서드를 살펴봅시다. List 계열의 모든 클래스는 List 인터페이스의 추상 메서드를 구현했기때문에 각 클래스의 고유 멤버를 제외한 나머지 핵심 기능은 사용방법이 모두 동일합니다.   

> API Docs : [https://docs.oracle.com/javase/8/docs/api/java/util/List.html](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)
```java
boolean	add(E e)
Appends the specified element to the end of this list (optional operation).
void	add(int index, E element)
Inserts the specified element at the specified position in this list (optional operation).
boolean	addAll(Collection<? extends E> c)
Appends all of the elements in the specified collection to the end of this list, in the order that they are returned by the specified collection's iterator (optional operation).
boolean	addAll(int index, Collection<? extends E> c)
Inserts all of the elements in the specified collection into this list at the specified position (optional operation).
void	clear()
Removes all of the elements from this list (optional operation).
boolean	contains(Object o)
Returns true if this list contains the specified element.
boolean	containsAll(Collection<?> c)
Returns true if this list contains all of the elements of the specified collection.
boolean	equals(Object o)
Compares the specified object with this list for equality.
E	get(int index)
Returns the element at the specified position in this list.
int	hashCode()
Returns the hash code value for this list.
int	indexOf(Object o)
Returns the index of the first occurrence of the specified element in this list, or -1 if this list does not contain the element.
boolean	isEmpty()
Returns true if this list contains no elements.
Iterator<E>	iterator()
Returns an iterator over the elements in this list in proper sequence.
int	lastIndexOf(Object o)
Returns the index of the last occurrence of the specified element in this list, or -1 if this list does not contain the element.
ListIterator<E>	listIterator()
Returns a list iterator over the elements in this list (in proper sequence).
ListIterator<E>	listIterator(int index)
Returns a list iterator over the elements in this list (in proper sequence), starting at the specified position in the list.
E	remove(int index)
Removes the element at the specified position in this list (optional operation).
boolean	remove(Object o)
Removes the first occurrence of the specified element from this list, if it is present (optional operation).
boolean	removeAll(Collection<?> c)
Removes from this list all of its elements that are contained in the specified collection (optional operation).
default void	replaceAll(UnaryOperator<E> operator)
Replaces each element of this list with the result of applying the operator to that element.
boolean	retainAll(Collection<?> c)
Retains only the elements in this list that are contained in the specified collection (optional operation).
E	set(int index, E element)
Replaces the element at the specified position in this list with the specified element (optional operation).
int	size()
Returns the number of elements in this list.
default void	sort(Comparator<? super E> c)
Sorts this list according to the order induced by the specified Comparator.
default Spliterator<E>	spliterator()
Creates a Spliterator over the elements in this list.
List<E>	subList(int fromIndex, int toIndex)
Returns a view of the portion of this list between the specified fromIndex, inclusive, and toIndex, exclusive.
Object[]	toArray()
Returns an array containing all of the elements in this list in proper sequence (from first to last element).
<T> T[]	toArray(T[] a)
Returns an array containing all of the elements in this list in proper sequence (from first to last element); the runtime type of the returned array is that of the specified array.
```
