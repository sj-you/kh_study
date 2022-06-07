# 인터페이스  

- Consumer 인터페이스
    
  _매개값만 있고 리턴값이 없는 추상메소드를 가졌다._  
  *데이터를 받고 반환하지 않는 타입이 있을때 사용가능 ( 소비한다 )*  
  ```java
  Consumer<String> consumer = t -> System.out.println(t + "8");
  consumer.accept("java");

  BiConsumer<String, String> biConsumer = (t, u) -> System.out.println(t + u);
  biConsumer.accept("java", "8");

  DoubleConsumer doubleConsumer = d -> System.out.println("java" + d);
  doubleConsumer.accept(8.0);

  ObjIntConsumer<String> objIntConsumer = (t, i) -> System.out.println(t+i);
  objIntConsumer.accept("java", 8);
  
  // 출력결과 : java8
  ```  
  
- Supplier  
    *매개값은 없고 리턴값만 있는 추상 메소드를 가짐*
  ```java
  IntSupplier intSupplier = () -> {
    int num = (int) (Math.random() * 6) + 1;
    return num;
  };

  int num = intSupplier.getAsInt();
  System.out.println("눈의 수 : " + num);
  ```  
  
- Function 인터페이스  
*매개값과 리턴값이 모두 있는 추상 메소드를 가진다*  
*주로 매개값을 리턴값으로 매핑(타입변환) 할 경우 사용*  

    ```java
    printString( t -> t.getName() ); 	// 학생이름으로 반환

    public static void printString(Function<Student, String> function) {
                for(Student student : list) {
                    System.out.print(function.apply(student) + " ");
                }
                System.out.println();
            }; // printString
    ```
