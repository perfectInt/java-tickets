## Список заданий 1

### 1. Напишите программу на Java, чтобы поменять местами значения, хранящиеся в двух переменных, без использования третьей переменной.
```
import java.util.Scanner;

public class FourthTask {
   public static void main(String args[]) {
      int a, b;
      System.out.println("Введите нужные значения a и b");
      Scanner scannerQ = new Scanner(System.in);
      a = scannerQ.nextInt();
      b = scannerQ.nextInt();
 
      System.out.println("До обмена значениями\na = "+a+"\nb = "+b);
 
      a = a + b;
      b = a - b;
      a = a - b;
 
      System.out.println("После обмена значениями без промежуточной переменной\na = "+a+"\nb = "+b);
   }
}
```

### 2. Напишите программу на Java для подсчета количества конкретных слов в строке, используя HashMap.
```
import java.util.HashMap;

public class FifthTask {
        public static void main(String[] args) {
               String st = "Current task posted for Java developers developers";
               String[] words = st.split(" ");
               HashMap<String,Integer> keyValue = new HashMap<String,Integer>();
               for (int i=0; i<= words.length-1; i++) {
                       if (keyValue.containsKey(words[i])) {
                               int counter = keyValue.get(words[i]);
                               keyValue.put(words[i], counter+1);
                       }
                       else {
                               keyValue.put(words[i], 1);
                       }
               }
               System.out.println(keyValue);
        }
}
```
