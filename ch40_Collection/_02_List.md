# java.util.List
## 1. List 의 특징
List의 특징은 다음과 같습니다.   
><pre>선형 구조<br>인덱스 있음<br>중복 원소 저장 가능</pre>
List 계열의 클래스들은 선형으로 원소를 저장합니다. Array 라는 단어가 들어간 클래스는 원소를 저장할 때 배열을 사용하고,<br>Linked 가 들어가는 클래스들은 연결리스트를 사용합니다. <br>
중복되는 원소가 저장되어도 인덱스로 구분이 가능하기 때문에 중복 저장을 허용합니다.
## 2. List 의 주요 구현 클래스
### 2.1 java.util.ArrayList 

### 2.2 java.util.LinkedList
### 2.3 java.util.Vector
### 2.4 java.util.Stack
## 3. List 의 주요 메서드 
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
다른 컬렉션 객체 c의 모든 원소를 **한꺼번에 추가**합니다. 리스트에 변화가 생긴 경우 (즉, 정상적으로 추가된 경우) true를 return합니다.
<br><br><br>
```java
boolean	addAll(int index, Collection<? extends E> c)
```
다른 컬렉션 객체 c의 모든 원소를 index 번 위치에 순서대로 **한꺼번에 삽입**합니다. 리스트에 변화가 생긴 경우 true를 return합니다.
### 원소 삭제
```java
void	clear()
```
모든 원소를 삭제합니다.
<br><br><br>

### 원소 확인
```java
boolean	contains(Object o)
```
o가 리스트에 있으면 true를 return합니다.
<br><br><br>

```java
boolean	containsAll(Collection<?> c)
```
컬렉션 객체 c가 리스트에 있으면 true를 return합니다.
<br><br><br>

```java
int	indexOf(Object o)
```
o가 위치한 인덱스를 return 합니다. (o가 리스트에 여러 개 있다면 가장 앞에 위치한 o의 인덱스) o가 리스트에 없다면 -1을 반환합니다.
<br><br><br>


```java
int	lastIndexOf(Object o)
```
마지막 o가 위치한 인덱스를 return 합니다. (o가 리스트에 여러 개 있다면 가장 뒤에 위치한 o의 인덱스) o가 리스트에 없다면 -1을 반환합니다.

```java
boolean	isEmpty()
```
빈 리스트면 true를 return합니다.
<br><br><br>

### 원소 받기
```java
E	get(int index)
```
index 번에 위치한 원소를 return합니다. 인덱스가 범위를 벗어난 경우 IndexOutOfBoundsException을 던집니다.
<br><br><br>

### 이터레이터 받기
```java
Iterator<E>	iterator()
```
리스트의 Iterator 객체를 return 합니다.
<br><br><br>

```java
ListIterator<E>	listIterator()
```
리스트의 ListIterator 객체를 return 합니다.
<br><br><br>

```java
ListIterator<E>	listIterator(int index)
```
index 번 원소부터 반복 수행 할 ListIterator 객체를 return 합니다.
<br><br><br>
### 원소 삭제
```java
E	remove(int index)
```
index번에 위치한 원소를 삭제하고 삭제된 원소를 return합니다.
<br><br><br>
```java
boolean	remove(Object o)
```
특정 원소 o를 삭제합니다. o가 리스트에 여러 개 있는 경우 가장 앞에 위치한 o를 삭제합니다.
삭제를 수행했을 경우 true를, 삭제가 수행되지 않았다면 false를 return합니다.
<br><br><br>
```java
boolean	removeAll(Collection<?> c)
```
컬렉션 c 에 해당하는 모든 원소를 리스트에서 삭제합니다.
삭제를 수행했을 경우 true를, 삭제가 수행되지 않았다면 false를 return합니다.
<br><br><br>
```java
boolean	retainAll(Collection<?> c)
```
다른 컬렉션 객체 c의 교집합에 해당하는 원소만 남기고 모두 삭제합니다.   
예를 들어 리스트 a에 {1, 2, 3, 4}가 있고 b에 {2, 4, 6, 8}이 있다고 가정 했을 때 a.retainAll(b) 호출한다면 a는 {2, 4} 만 남게 됩니다.
<br><br><br>

```java
List<E>	subList(int fromIndex, int toIndex)
```
fromIndex <= 인덱스 < toIndex 에 해당하는 원소들만 추출하여 이를 List에 담아 return합니다. 
<br><br><br>

### 원소 대체
```java
default void	replaceAll(UnaryOperator<E> operator)
```
operator 를 사용하여 모든 원소를 수정합니다. (참고: UnaryOperator 는 single parameter를 가진 람다 함수의 객체형 클래스입니다.)
오홍 default 메서드네요, 그렇다면 구현클래스에서는 따로 오버라이드를 안했을 가능성이 있네요.
<br><br><br>

```java
E	set(int index, E e)
```
index번 위치의 원소를 e로 대체합니다. 대체된 이전 원소를 return합니다.
<br><br><br>

### 원소 개수
```java
int	size()
```
현재 리스트에 저장된 원소 개수를 return합니다.
<br><br><br>

### 원소 정렬
```java
default void	sort(Comparator<? super E> c)
```
Comparator C에 지정된 내용대로 대상을 정렬합니다.
<br><br><br>

### 기타
```java
default Spliterator<E>	spliterator()
```
전체 원소들에 대한 Spliterator 객체를 return합니다. (참고. Spliterator는 대상의 병렬 처리를 위해 사용합니다.)
<br><br><br>

### 배열로 
```java
Object[]	toArray()
```
리스트의 원소들을 Object[] 배열에 담아 이를 return합니다.
<br><br><br>
```java
<T> T[]	toArray(T[] a)
```
리스트의 길이가  a 배열의 길이와 같다면 a에 담고 이를 return합니다.   
만약 길이가 다르다면 a 를 그대로 두는 대신 새로운 배열을 생성하여 이를 return합니다.
