# Common-Programming-Questions-Solutions


### Q.1 - FizzBuzz problem regarding multiple of 3 and 5
```
public class FizzBuzzTest{
    public static void main(String args[]){
        for(int i = 1; i <= 50; i++) {
            if(i % (3*5) == 0) System.out.println("FizzBuzz");
            else if(i % 5 == 0) System.out.println("Buzz");
            else if(i % 3 == 0) System.out.println("Fizz");
            else System.out.println(i);
        } 
    } 
}
```
