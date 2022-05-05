# __이진희의 일기__
### __차례__

 - 기본 정보
     - 학적사항
 - 오늘의 할 일
    - java stack 구현 연습하기


### __기본정보__
 _저는 전북대학교 소프트웨어공학과 21학번 이진희입니다._

### __오늘 할 일__
_5월 1주차 java programming 강의에 나온 stack 구현을 연습하겠습니다._

```java
public interface Stack {
	int length();//stack의 크기 반환
    Object pop(); //삭제 및 반환
    boolean push(Object ob); //삽입
}

public class StringStack implements Stack {
	String array[] = new String[10];
	private int len=0;
	private int size = 10;
	
	@Override
	public int length() {
		return size;
	}

	@Override
	public Object pop() {
		String ans = array[len-1];
		array[len-1] = null;
		len--;
		return ans;
	}

	@Override
	public boolean push(Object ob) {
		if (len<size) {
			array[len] = (String)ob;
			len++;
			return true;
		}
		else {
			return false;
		}
	}
}

import java.util.*;

public class ExerMain {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Scanner s = new Scanner(System.in);
		Stack stack = new StringStack();
		
		System.out.println("Please input 10 elements");
		for (int i=0; i<stack.length(); i++) {
			if (stack.push(s.next()) == false) break;
		}
		
		System.out.println("Full stack. Now start 'pop'");
		for (int i=0; i<stack.length(); i++) {
			System.out.print(stack.pop()+ " ");
		}
		s.close();
	}

}
```