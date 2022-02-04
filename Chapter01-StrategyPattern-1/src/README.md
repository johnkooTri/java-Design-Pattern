## 전략 패턴(Strategy Pattern)

다른객체의 기능을 사용한는 것. 위임하다.

 - **인터페이스 개념**:기능의 선언과 구현을 분리, 어떤한 기능의 호출하는 통로

 - **델리게이트**:특정객체의 기능을 사용하기 위해 , 다른객체의 기능을 호출하는것

 - **스트레티지 패턴**:전략 패턴은 같은 문제를 해결하는 여러 알고리즘이 클래스별로 캡슐화되어 있고 이들이 필요할 때 교체할 수 있도록 함으로써 동일한 문제를 다른 알고리즘으로 해결할 수 있게 하는 디자인 패턴이다.

![image](https://user-images.githubusercontent.com/87956185/152537871-048492e2-ca39-4a08-af22-9880606eb500.png)



> 게임캐릭터 클래스


	
	public class GameCharacter {
			//접근점   
	 		private Weapon weapon;

			public int attact() {

				return weapon.doAttact();
			}

           //교환가능
			public void setWeapon(Weapon weapon) {
				this.weapon = weapon;
			}

		}

> 무기를 추가할때 편리하다.
> 게임캐릭터가 weapon 전략을 가지고 있고 weapon통해서 공격이 들어갈때
> weapon에 따라 호출하는게 다르다.

	public class Application {

	public static void main(String[] args) {
		
		GameCharacter character = new GameCharacter();
		
		character.setWeapon(new Sword());
		character.attact();
		
		character.setWeapon(new Ax());
		character.attact();
		
		character.setWeapon(new Knife());
		character.attact();
	}
	
}


![image](https://user-images.githubusercontent.com/87956185/152542959-34e1b0c2-bb4a-4cde-ac07-77293c664e5f.png)
