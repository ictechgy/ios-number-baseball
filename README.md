# 숫자야구 프로젝트 저장소

## Step0 - Flow Chart

![ios-baseball-diagram](https://user-images.githubusercontent.com/39452092/119670193-a85b3c00-be73-11eb-8ef6-af3229a1258d.png)

### 🤩 Details

- [draw.io](https://draw.io)를 통해 flow chart를 그림
- 각 함수별로 나누어서 그리고자 하였음
- Flow chart에 대한 기본 규칙은 [위키백과](https://ko.wikipedia.org/wiki/%EC%88%9C%EC%84%9C%EB%8F%84)를 통해 학습하였다.



## Step1

### 📖 주요 학습 개념

- **`Set` Collection Type**
  - Set 는 중복을 허용하지 않고 순서가 존재하지 않는 타입이다. 
  - Set에 저장하려는 타입은 무조건 Hashable해야 한다. 
  - 기본 타입인 String, Int, Double, Bool, 연관 값이 존재하지 않는 Enumeration들은 모두 Hashable하다.
  - 만약 사용자 정의 타입을 Set에 넣고 싶다면 해당 타입은 protocol Hashable을 채택해야만 한다.

- **Swift API Design Guideline**

  - 특히 Naming에 대한 부분을 중점적으로 살펴보았다. 

    - 변수명은 타입이름을 포함시키기 보다는 기능(role)에 따라 명명하기
    - 함수명은 get으로 시작하지 않기

    ```swift
    //좋은 예:
    func name(for user: User) -> String?
    //나쁜 예:
    func getName(for user: User) -> String?
    ```

    > [Reference: Awesome Open Source](https://awesomeopensource.com/project/StyleShare/swift-style-guide#%ED%81%B4%EB%A1%9C%EC%A0%80)

    - Side-Effect에 따라 함수나 메소드 명명(값을 직접적으로 바꾸느냐 그렇지 않느냐에 따라)

- **내장 함수**

  * **map(_:)** - map내장함수를 공부하고 적용해 보았다.

    [Apple Developer Documentation](https://developer.apple.com/documentation/swift/array/3017522-map)

    '시퀀스의 요소들에 대해 주어진 클로저를 적용한 결과가 배열로 반환됩니다.'

    매핑 클로저를 통해 요소 하나하나들에 변환을 수행하여 새로운 배열을 반환받고 싶을 때 사용한다.

    ```swift
    func map<T>(_ transform: (Element) throws -> T) rethrows -> [T]
    ```

  * **joined(separator:)**

    [Apple Developer Documentation](https://developer.apple.com/documentation/swift/array/1690077-joined)

    시퀀스 각각의 요소 값 사이에 separator를 삽입한 뒤 하나로 만들어 반환

    ```swift
    func joined<Separator>(separator: Separator) -> JoinedSequence<Array<Element>> where Separator : Sequence, Separator.Element == Element.Element
    ```

    선언 역시 복잡하다.

    반환타입은 JoinedSequence타입이며 Separator 타입은 Sequence 프로토콜을 준수해야 하고 Separator의 Element타입과 Array의 Element 타입이 일치해야 한다.

    

### 😭 노력하였으나 잘 되지 않은 점

- **Naming**
  - 의미가 잘 전달되는 좋은 이름을 지어보고자 하였지만 쉽지 않았다.
  - 네이밍에 있어서 프로젝트와 관련있게 이름을 짓는 것도 생각해볼만 했다.
- **함수의 기능 분리**
  - 함수를 기능별로 분리하고자 하였지만 100% 전부 잘 적용하지는 못한 것 같다. 일관성도 조금 부족했다.
