# Integer to Roman
<h3>Write a program to convert Integer to Roman Numericals.<br></h3>

<pre><p style="font-size:79px">
  Integer to Roman <br>
  1 - I             8 - VIII <br>
  2 - II            9 - IX <br>
  3 - III           10 - X <br>
  4 - IV            50 - L <br>
  5 - V             100 - C <br>
  6 - VI            500 - D <br>
  7 - VII           1000 - M <br>
</p></pre>

Input:

```python
Enter Integer: 152
```

Output:

```python
CLII
```
import java.util.*;

public class integerToRoman {

    public static void main(String [] args){

        Scanner scanner = new Scanner(System.in);
        
        System.out.println("Enter Integer:");  // Taking the input numerals
        int num = scanner.nextInt();
        
        System.out.println(intToRoman(num)); // printing the output as Roman Number

    }

    public static String intToRoman(int num) {

        // Using Map Function to take the values of Roman and Integer as Key-value pair

        Map<String, Integer> mp = new LinkedHashMap<>();
        mp.put("M", 1000);
        mp.put("CM", 900);
        mp.put("D", 500);
        mp.put("CD", 400);
        mp.put("C", 100);
        mp.put("XC", 90);
        mp.put("L", 50);
        mp.put("XL", 40);
        mp.put("X", 10);
        mp.put("IX", 9);
        mp.put("V", 5);
        mp.put("IV", 4);
        mp.put("I", 1);

        StringBuilder sb = new StringBuilder();

        for(Map.Entry<String, Integer> entry : mp.entrySet()) {

            while(num >= entry.getValue()) {

                num -= entry.getValue();     //Subtract num with value[i] till num is greater than Zero,
                sb.append(entry.getKey());   // if num is greater/equal to value[i], and append Corresponding symbol
            }
        }
        return sb.toString();     // otherwise just move lower value
    }


}

