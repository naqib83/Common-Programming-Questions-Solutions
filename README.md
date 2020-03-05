# Common-Programming-Questions-Solutions


#### 1. FizzBuzz problem regarding multiple of 3 and 5

```
    for(int i = 1; i <= 50; i++) {
        if(i % (3*5) == 0) System.out.println("FizzBuzz");
        else if(i % 5 == 0) System.out.println("Buzz");
        else if(i % 3 == 0) System.out.println("Fizz");
        else System.out.println(i);
    } 
```

#### 2. How to sort an array of integers by their frequency

```
int[] intArray = {7, 1, 3, 4, 7, 1, 7, 1, 4, 5, 1, 9, 3};
        Map<Integer, Integer> elementCountMap = new LinkedHashMap<>();
       
        for(int i = 0; i<intArray.length; i++){
            if(elementCountMap.containsKey(intArray[i])){
                elementCountMap.put(intArray[i], elementCountMap.get(intArray[i])+1);
            } else {
                elementCountMap.put(intArray[i], 1);
            }
        }
        
        ArrayList<Entry<Integer, Integer>> listOfEntry = new ArrayList<>(elementCountMap.entrySet());
        Collections.sort(listOfEntry, (ent1, ent2) -> ent2.getValue().compareTo(ent1.getValue()));
        
        for(Entry<Integer, Integer> entry : listOfEntry){
            int frequency = entry.getValue();
            
            while(frequency >= 1){
                System.out.print(entry.getKey() +" ");
                frequency--;
            }
        }
```
