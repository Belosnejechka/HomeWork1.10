## Задание 1

public class JvmComprehension { 
// -1 ClassLoader загружает класс JvmComprehension, методы этого класса и помещает информацию в MetaSpase

public static void main(String[] args) { 
// 0 в стеке создается фрйем main
        int i = 1;                      
        // 1 i попадет в стек фрема main
        Object o = new Object();        
        // 2 o попадает в кучу, а в стек ферма main попадет переменная с сылкой на созданный объект в куче
        Integer ii = 2;                 
        // 3 o попадает в кучу, а в стек ферма main попадет переменная с сылкой на созданный объект в куче
        printAll(o, i, ii);             
        // 4 в момент вызова метода в стек поверх фрейма main добавится новый фрейм printAll, в нем содаются переменные o i ii с сылками на кучу
        System.out.println("finished"); 
        // 7 фрейм printAll ушел из стека теперь в момент вызова метода в стек поверх фрейма main добавится новый фрейм printLn в который передадим ссылку на String из кучи,
    }                                   
    // 8 далее фрейм println уйдет из стека, а вслед за ним и фейрм main
// 9 Из за простоты данной программы она завершиться раньше чем начнется сборка мусора.

private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;                   
        // 5 o попадает в кучу, а в стек ферма printAll попадет переменная с сылкой на созданный объект в куче
        System.out.println(o.toString() + i + ii);  
        // 6 в момент вызова метода в стек поверх фрейма printAll добавится новый фрейм printLn,
        в нем создаются переменные i ii с сылками на кучу,
        для o будет вызван фрейм toString поверх фрейма printLn который создаст ссылку на кучу с переменной о
        фрейм toStirng передаст во фрейм println ссылку на переменну в куче и уйдет из стека, далее выполниться фрейм println и так же уйдет из стека


## Задание 2 
<img width="1710" alt="Screenshot 2024-04-22 at 21 17 55" src="https://github.com/Belosnejechka/HomeWork1.10/assets/153391631/8aeeb833-b0b7-4261-8e79-2c7c45f0ee2c">
На скриншоте отчетливо видно как подгружаются классы и наполняется 'MetaSpace'
<img width="1710" alt="Screenshot 2024-04-22 at 21 18 05" src="https://github.com/Belosnejechka/HomeWork1.10/assets/153391631/4c46186e-977f-474a-a2e4-31ae72d989b5">
На втором скриншоте так же очетливо видно наполнение 'Heap' в 3 этапа в те момент когда программа создает объекты

