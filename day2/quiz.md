
# [4-7] 인터페이스, 유니언타입, 인터섹션타입, 타입별칭

> 👩‍ 담당자: 류재경<br/>

<br/><br/>

# 퀴즈_1
인터페이스, 유니언타입, 인터섹션타입, 그리고 타입별칭을 사용하여 다음 문제를 해결하시오.

1) Person 이라는 인터페이스를 만드시오. 
이 인터페이스는 name(string), age(number), hobby(string[])라는 프로퍼티를 가져야함
    ```typescript
    interface Person {
            name: string;
            age: number;
            hobby: string[];
        }   
    ```

2) Employee 라는 인터페이스를 만드시오. 
이 인터페이스는 position(string), workYears(number)라는 프로퍼티를 가져야함.
    ```typescript
    interface Employee {
        position: string,
        workYears: number,
    }
    ```

3) Person과 Employee 인터페이스를 합친 PersonEmployee 인터섹션 타입을 만드세요.
    ```typescript
    type PersonEmployee = Person & Employee;
    ```

4) 유니언 타입인 AnimalOrPerson을 만드시오. 
이 유니언 타입은 string 또는 Person 타입을 가져야함
    ```typescript
    type AnimalOrPerson = string | Person;
    ```

5) 타입 별칭을 이용하여 AgeType이라는 타입을 만드시오. 
    AgeType은 숫자 또는 "unknown"이 될 수 있음
    ```typescript
    type AgeType = number | "unknown";
    ```
 

 <br/><br/>

# 퀴즈_2
인터페이스, 유니언타입, 인터섹션타입, 그리고 타입별칭을 사용하여 다음 문제를 해결하시오.
1) Vehicle 인터페이스를 만드시오. 
이 인터페이스는 make (string), model (string), year (number)라는 프로퍼티를 가져야함
    ```typescript
    interface Vehicle {
        make: string;
        model: string;
        year: number;
    }
    ```

2) TwoWheeler와 FourWheeler라는 두 인터페이스를 만드시오. 
TwoWheeler는 type이 'motorcycle'이고, FourWheeler는 type이 'car'인 추가 프로퍼티를 가져야함
    ```typescript
    interface TwoWheeler {
        type : 'motorcycle', 
    }
    interface FourWheeler {
        type: 'car'
    }
    ```

3) Vehicle과 TwoWheeler 또는 FourWheeler를 결합한 VehicleType라는 인터섹션 타입을 만드시오.
    ```typescript
    type VehicleType = Vehicle & ( TwoWheeler | FourWheeler);
    ```

4) VehicleType의 type 프로퍼티를 기반으로 하는 유니언 타입 VehicleUnionType을 만드시오.
    ```typescript
    type VehicleUnionType = VehicleType['type'];
    ```

5) 타입 별칭을 이용하여 MakerType이라는 타입을 만드시오. 
MakerType은 string 또는 null이 될수있음
    ```typescript
    type MakerType = string | null;
    ```

 <br/><br/>

# 퀴즈_3
인터페이스, 유니언타입, 인터섹션타입, 그리고 타입별칭을 사용하여 다음 문제를 해결하시오.
1) Shape라는 이름의 인터페이스를 만들어 주시오. 
이 인터페이스는 color라는 이름의 string 타입 프로퍼티를 가지고 있어야함.
    ```typescript
    interface Shape {
        color: string;
    }
    ```

2) Circle이라는 이름의 인터페이스를 만들어 주시오. 
이 인터페이스는 Shape 인터페이스를 상속하고, radius라는 이름의 number 타입 프로퍼티와 center라는 optional 프로퍼티를 가지고 있어야함. 
center 프로퍼티는 x, y를 가지고 있고 둘다 number 타입임
    ```typescript
    interface Circle extends Shape {
        radius: number,
        center?: {
            x: number,
            y: number,
        }
    }
    ```

3) ShapeCollection이라는 이름의 인터페이스를 만들어 주시오. 
이 인터페이스는 string 타입의 key를 가진 Shape를 value로 가지는 프로퍼티를 가질 수 있어야함
    ```typescript
    interface ShapeCollection {
        [key: string] : Shape
    }
    ```
