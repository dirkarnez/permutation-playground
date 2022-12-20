permutation-playground
======================
```java
import java.util.*;

public class MyClass {
    public static void main(String args[]) {
        List<String> results = new ArrayList<String>();
        String test_str = "abcd";
        char[] chars = test_str.toCharArray();
        results.add(new String("" + chars[0]));
        for(int j=1; j<chars.length; j++) {
            char c = chars[j];
            int cur_size = results.size();
            //create new permutations combing char 'c' with each of the existing permutations
            for(int i=cur_size-1; i>=0; i--) {
                String str = results.remove(i);
                for(int l=0; l<=str.length(); l++) {
                    results.add(str.substring(0,l) + c + str.substring(l));
                }
            }
        }
        System.out.println("Number of Permutations: " + results.size());
        System.out.println(results);
    }
}
```

```python
from itertools import permutations

for a in permutations("ABCD", 4):
   print(f"{a}")
```

### Reference
- **https://stackoverflow.com/questions/11915026/permutations-of-a-string-using-iteration**
- **https://www.geeksforgeeks.org/permutations-string-using-iteration/**
