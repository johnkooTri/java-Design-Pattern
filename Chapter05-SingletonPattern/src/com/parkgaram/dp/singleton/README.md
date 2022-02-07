## 싱글턴 패턴(Singleton Pattern)


인스턴스가 오직 하나만 생성되는 것을 보장하고, 어디에서든 이 인스턴스에 접근할 수 있도록 하는 디자인 패턴이다

- 객체:속성과기능을 갖춘것

- 클래스:속성과 기능을 정의한것

- 인스턴스: 속성과기능을 가진것 중 실제하는것

![image](https://user-images.githubusercontent.com/87956185/152806761-ac5bf632-7043-465f-a9af-eb6dc7e60228.png)


단 하나의 객체만 생성해 이를 어디에서든지 참조할 수 있게 만드는 것

    public class SomeSystemComponent {

        private static SomeSystemComponent instance;

        private SomeSystemComponent() {

        }

        public static SomeSystemComponent getInstance(){
          if (instance == null) {

          }else {
            instance = new SomeSystemComponent();
          }
          return instance;
        }
    }

주목해야할 점은 getInstance() 메서드가 static으로 선언되어 있다는 것이다. 정적 메서드는 구체적인 인스턴스 영역에 속하는 영역이 아니고 클래스 자체에 속한다는 의미이다. 따라서 클래스의 인스턴스를 통하지 않고서도 메서드를 실행할 수 있고 변수를 참조할 수 있다.
