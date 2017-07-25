```java
import java.util.HashMap;
import java.util.Map;

public class MapProjectSolution {

    static Map<Integer, Long> fibonacciNums = new HashMap<>();

    public static void initMap () {
        fibonacciNums.put(0, 0l);
        fibonacciNums.put(1, 1l);
    }

    public static long calcFibonacci (int index) {
        if (fibonacciNums.containsKey(index)) {
            return fibonacciNums.get(index);
        }
        long response = calcFibonacci(index - 1) + calcFibonacci(index - 2);
        fibonacciNums.put(index, response);
        return response;
    }

    public static void main(String[] args) {
        initMap();

        long startTime;
        long endTime;

        startTime = System.currentTimeMillis();
        for (int i = 0; i < 50; i++) {
            System.out.println("calc(" + i + ") = " + calcFibonacci(i));
        }
        endTime = System.currentTimeMillis();

        System.out.println("50 Fibonacci numbers took " + (endTime - startTime) + " milliseconds");

    }
}
```
