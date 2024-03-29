# Collection Framework

## 1. Collection Framework란?
[**컬렉션 프레임워크**](https://docs.oracle.com/javase/8/docs/technotes/guides/collections/overview.html)는 **대량의 데이터를 저장, 처리**하기 위한 클래스들의 집합입니다.   
쉽게 생각해 **배열의 단점**을 보완하기 위해 나온 배열의 대체품으로 생각하면 됩니다. 배열은 한 개 이상의 데이터를 저장하기 위한 서랍장 역할의 메모리였습니다. 컬렉션 객체도 마찬가지로 여러 데이터를 저장하기 위한 창고의 역할을 합니다. 다만 이 창고의 모양과 종류가 굉장히 다양합니다.
컬렉션에 본격적으로 들어가기 전에 배열의 단점으로 어떤 것이 있었는지 먼저 생각해봅시다. 배열의 한계를 안다면 컬렉션을 더욱 잘 이해할 수 있겠죠?

------------------------------------------
### 배열의 단점 
#### 1. 변경 불가능한 용량.
자바의 배열은 정적할당(stack 영역) ~~C, C++의 기본 배열은 stack에 할당되지요.~~ 보다 비교적 할당이 자유로운 동적할당 메모리(heap 영역)를 사용합니다.   
그럼에도 jvm은 배열을 한 번 생성한 이후부터는 그 배열의 크기를 줄이거나 늘이지 않습니다. 혹시나 배열에 이웃한 메모리에 또다른 중요한 데이터가 있을지 모르잖아요?   
따라서 용량을 초과하는 더 많은 원소를 저장하거나 빈 칸을 지우는 등의 배열 사이즈의 변경을 위해서라면, 새 배열을 생성 한 뒤 기존 원소를 그대로 복사해야 하는 번거로움이 있습니다. 이 경우 메모리를 더 사용해야 하고 원소를 복사하기위한 loop문이 사용된다는 불리점이 생기겠죠.      
결국 배열은 **원소의 개수를 모르는 상황**에서 사용하기엔 불편한 점이 굉장히 많습니다.   
이러한 배경으로 컬렉션에서는 배열의 크기를 자동으로 키워주는, 우리 입장에서는 무제한 배열처럼 느껴지는 [**java.util.ArrayList**](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html) 클래스가 있습니다!

#### 2. 물리적인 구조
배열은 동일한 자료형의 메모리가 연속적으로 배치되어있는 구조로 몇몇 상황에서 다음과 같은 문제가 발생합니다. <br>
>(1) 원소를 **삽입**하는 경우 
><pre>삽입할 위치가 맨 앞, 혹은 중간이라면<br>빈 칸을 만들기 위하여 삽입할 위치 이후의 원소들을 <b>하나씩 밀어내는</b> 재배치 작업이 필요합니다.<br>밀어내는 작업을 위해 loop를 진행해야 하는데요, 여기서 끝이 아닙니다. <br>마지막 칸까지 원소가 있는 완전 포화 상태에서는 단순하게 밀어내기만 한다면 마지막 원소는 사라져버리겠죠? <br>따라서 이를 방지하는 추가 분기문이 필요합니다.</pre>

>(2) 원소를 **삭제**하는 경우
><pre>특정 원소를 삭제하는 데에 가장 좋은 방법은 <br>원소들을 <b>하나씩 당겨주면서</b> 원하는 원소를 삭제하는 방법인데요. <br>이 또한 원소를 옮기는 loop문이 필요합니다. <br>이후 원소들의 끝자락을 0 혹은 null 로 두면서 삭제 작업을 끝냅니다.
</pre>   

이러한 단점이 **연결리스트**라는 논리적 선형 구조의 등장 배경이 되었죠.    
컬렉션은 **이중연결리스트** 형태의 [**java.util.LinkedList**](https://docs.oracle.com/javase/8/docs/api/java/util/LinkedList.html)클래스를 제공합니다.

#### 3. 선형 구조로서의 제약 사항 
배열과 앞서 보았던 연결리스트 두 구조는 선형 구조에 해당합니다. 이는 원소가 일렬로 배치되어있는 구조를 말하는데요.    
일렬배치로 인한 단점이 또 있네요. 바로 **검색**입니다.
><pre>정렬되지 않은 선형구조는 특정 원소를 검색하는 것에 있어 첫 원소부터 마지막 원소까지를 모두 확인해야 하는 과정이 필요합니다.<br>즉, 1000개의 원소가 있으면 최악의 경우 1000번째 실행에서 원하는 원소를 찾는다는 의미이죠.<br>이러한 단순 무식한 방법은 검색해야 하는 데이터가 많을 수록 불리해집니다.</pre>	
검색을 더욱 효율적으로 하기 위해 Tree, Map, Hash 등의 **비선형구조**가 등장했습니다. 

------------------------------------------
## 2. Collection Framework의 특징
### 2.1. 모든 원소는 Object 형으로 저장한다.   
모든 타입의 원소를 소화할 수 있도록 원소의 자료형을 Object로 받습니다.   
단, Generic을 통해 자료형을 특정할 수 있습니다.

### 2.2. 빠른 퍼포먼스와 효율적인 메모리 관리가 가능하다
자바가 작정하고 만든 라이브러리입니다. 믿고 사용하세요. ㅎㅎ

### 2.3. 원소를 무제한으로 저장할 수 있다.
컬렉션 객체들은 용량을 초과하는 경우 내부에서 자동으로 그 길이를 늘립니다. 따라서 우리는 크기 걱정 없이 자유롭게 원소를 삽입, 삭제 할 수 있습니다.

## 3. Collection Framework의 종류
 컬렉션 프레임워크에 속하는 클래스는 수 십여개입니다. 다음은 그 중 대중적으로 사용되는 컬렉션 인터페이스와 클래스의 상속관계를 리스트 형태로 나타낸 것입니다.    
<ul>
<li>
Interface Collection
	<ul>
	<li>
	Interface Queue
	</li>
	<li>
	Interface List
		<ul>
		<li>
		Class ArrayList
		</li>
		<li>
		Class LinkedList
		</li>
		<li>
		Class Vector
			<ul>
			<li>
			Class Stack
			</li>
			</ul>
		</li>
		<li>
		Class LinkedList 
		</li>
		</ul>
	</li>
	<li>
	Interface Set
		<ul>
		<li>
		Class HashSet
		</li>
		<li>
		Class TreeSet
		</li>
		</ul>
	</li>
	</ul>
</li>
<li>	
Interface Map
	<ul>
	<li>
	Class HashMap
	</li>
	<li>
	Class TreeMap
	</li>
	<li>
	Class Hashtable
		<ul>
		<li>
		Class Properties
		</li>
		</ul>
	</li>
	</ul>
</li>
</ul>

 Collection 은 크게 두 개의 인터페이스로 나뉩니다. [java.util.Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)과 [java.util.Map](https://docs.oracle.com/javase/8/docs/api/java/util/Map.html)인데요.     
 Map은 Collection 인터페이스와 상속 관계가 아니기때문에 컬렉션 프레임워크에 해당하지는 않지만 관례상 컬렉션으로 분류합니다.    
 인터페이스들은 각기 다른 특징을 가지고 있습니다. 이를 반대로 말하면 우리가 객체화하여 사용할 컬렉션 클래스들은 그들의 특징에 따라 그에 맞는 인터페이스로 Categorize 되었다고 할 수 있죠.
 
### 2.1 java.util.List
><pre>선형 구조<br>인덱스 있음<br>중복 원소 저장 가능</pre>
### 2.2 java.util.Set
><pre>비선형 구조<br>인덱스 없음<br>중복 원소 저장 불가능</pre>
### 2.3 java.util.Queue
><pre>선형 FIFO 구조 (First In First Out, 선입선출)<br>인덱스 없음<br>중복 원소 저장 가능<br></pre>
### 2.4 java.util.Map
><pre>비선형 구조<br>'키(K)-값(V)' 쌍 단위로 원소를 저장<br>K를 통해 V에 접근. <br>인덱스 없음<br>K는 중복 불가능, V는 K가 다르면 중복 가능<br>List, Set, Queue 등의 다른 계열 클래스 중 가장 검색 속도가 빠름.</pre>
