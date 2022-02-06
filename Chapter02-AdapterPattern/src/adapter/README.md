## 어댑터 패턴(adapter patern)

한 클래스의 인터페이스를 클라이언트에서 사용하고자 하는 다른 인터페이스로 변환한다.

호환되지 않는 인터페이스를 사용하는 클라이언트를 그대로 활용할 수 있다.

- WHY ?? 

클라이언트와 구현된 인터페이스를 분리시킬 수 있으며, 향후 인터페이스가 바뀌더라도 그 변경내역은 어댑터에 캡슐화 되기 때문에 클라이언트는 바뀔 필요가 없어진다.


- 장점

관계가 없는 인터페이스 간 같이 사용가능하다.
프로그램 검사 용이
클래스 재활용성 증가


예)전기콘센트..

외국여행시 전기콘세트를 어댑터에 끼워서 사용 (해당플러그에서 필요로 하는 인터페이스로 바꿔준다.

![image](https://user-images.githubusercontent.com/87956185/152647479-6e7d65c3-b932-4e45-947d-e3af199607e1.png)
 
 ![image](https://user-images.githubusercontent.com/87956185/152648464-6c91ec24-bf02-4d06-89f8-b7c20d3f55c4.png)
 
 ![image](https://user-images.githubusercontent.com/87956185/152650016-3bffa230-0920-4a1d-8cca-6f5b8c04ca76.png)

 
 math 알고리즘을 사용해서 바꿔주기
 
 application class 에서 float num을 받아서 2배,절반 값을 구해야 하는데
 
     public class Application {


      public static void main(String[] args) {

        //요구사항을 수행하는 인스턴스
        Adapter target = new AdapterImpl();

        System.out.println(target.twiceOf(100.0f));
        System.out.println(target.halfOf(100.3f));

      }


    }
 
 
 Math 함수를 사용하여 adater를 만든다.
 Math.doubled 는 double 만 인자로 받게 되어있는데
 float이 들어오면 double 값으로 리턴되도록 오버라이드 한다.
 
     public class AdapterImpl implements Adapter {

      @Override
      public Double twiceOf(Float num) {
        return Math.doubled(num.doubleValue());
      }

      @Override
      public Double halfOf(Float num) {
        return Math.half(num);
      }
    }
    
    
    public interface Adapter {

      public Double twiceOf(Float num);

      public Double halfOf(Float num);
	
    }
