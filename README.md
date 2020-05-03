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

#### 3. Find a second maximum number from an integer array

```
int[] array = {2, 5, 5, 9, 8, 3, 4, 7};

// Initialize these to the smallest value possible
int highest = Integer.MIN_VALUE;
int secondHighest = Integer.MIN_VALUE;

// Loop over the array
for (int i = 0; i < array.length; i++) {

// If we've found a new highest number...
if (array[i] > highest) {
    //shift the current highest number to second highest
    secondHighest = highest;

    //and set the new highest.
    highest = array[i];
} else if (array[i] > secondHighest)
    //Just replace the second highest
    secondHighest = array[i];
}

System.out.println(secondHighest);
```

#### 4. Find common elements in two or three sorted arrays of integers

```
int[] arr1 = {1, 5, 10, 20, 40, 80};
int[] arr2 = {6, 7, 20, 80, 100};
int[] arr3 = {3, 4, 15, 20, 30, 70, 80, 120};

int x = 0, y = 0, z = 0;

while(x < arr1.length && y < arr2.length && x < arr3.length){

    if(arr1[x] == arr2[y] && arr2[y] == arr3[z]){
        System.out.println(arr1[x]);
        x++;
        y++;
        z++;
    } else if(arr1[x] > arr2[y]){
        y++;
    } else if(arr2[y] > arr3[z]){
        z++;
    } else {
        x++;
    }
}
```

#### 5. Reverse an array of integers

```
int[] arr1 = {1, 5, 10, 20, 40, 80};
        
for(int i =0; i< arr1.length/2; i++){
    int temp = arr1[i];
    arr1[i] = arr1[arr1.length-1-i];
    arr1[arr1.length-1-i] = temp;
}

//displaying
for(int k = 0; k<arr1.length; k++){
    System.out.print(arr1[k]+" ");
}
```

OR

```
int[] arr1 = {1, 5, 10, 20, 40, 80};
int[] arr2 = new int[arr1.length];

for(int i = arr1.length-1; i>=0; i--){
    arr2[arr1.length-1-i] = arr1[i];
}

//Just printing
for(int i = 0; i<arr1.length; i++){
    System.out.print(arr2[i]+" ");
}
```

#### 6. Reverse a string

```
String str = "grandforks";
char[] arr1 = str.toCharArray();

for(int i =0; i< arr1.length/2; i++){
    char temp = arr1[i];
    arr1[i] = arr1[arr1.length-1-i];
    arr1[arr1.length-1-i] = temp;
}

//displaying
for(int k = 0; k<arr1.length; k++){
    System.out.print(arr1[k]);
}
```

#### 7. How To Rotate An Array In The Left Direction by 2

```
int[] arr1 = {1, 5, 10, 20, 40, 80};
for(int i = 0; i<2; i++){
    int temp = arr1[0];
    for(int j = 0; j<arr1.length-1; j++){
        arr1[j] = arr1[j+1];
    }
    arr1[arr1.length-1] = temp;
}
for(int k = 0; k<arr1.length; k++){
    System.out.print(arr1[k]+" ");
}
```

#### 8. How to rotate an array in right direction by 2

```
int[] arr1 = {1, 5, 10, 20, 40, 80};
for(int i = 0; i<2; i++){
    int temp = arr1[arr1.length-1];
    for(int j = arr1.length-1; j>0; j--){
        arr1[j] = arr1[j-1];
    }
    arr1[0] = temp;
}
for(int k = 0; k<arr1.length; k++){
    System.out.print(arr1[k]+" ");
}
```

#### 9. Linear Search

#### 10. Find an element from an array of integers using Binary Search | The array must be sorted

*Iterative Solution

```
int[] arr = new int[] { 6, 28, 37, 44, 78, 88, 100, 110, 120, 150};
int find = 78;

int initial = 0; int last = arr.length - 1;
while( initial <= last){
    int mid = (initial + last)/2;

    if(arr[mid] == find) {
        System.out.println(mid);
    }

    if(arr[mid] > find) initial = mid+1;
    else last = mid-1; 
}
```

*Recursive Solution

```
public static int binarySearchRecursive(int[] arr, int start, int end, int find){

    int middle = (start + end)/2;

    if(end < start){
         return -1;
    } 

    if (arr[middle] > find){
        return binarySearchRecursive(arr, start, middle - 1, find);
    }

    if (arr[middle] < find){
        return binarySearchRecursive(arr, middle + 1, end, find);
    }

    if (search == arr[middle]){
        return middle;
    }
    
    return -1;
}
```

#### 11. How to sort an integer array without using Arrays.sort() OR (Bubble Sort)

```
int[] arr = new int[] { 6, 8, 7, 4, 312, 78, 54, 9, 12, 100, 89, 74 };

for (int i = 0; i < arr.length-1; i++) {
    for (int j = i + 1; j < arr.length-i-1; j++) {
        int tmp = 0;
        if (arr[i] > arr[j]) {
            tmp = arr[i];
            arr[i] = arr[j];
            arr[j] = tmp;
        }
    }
}

//Just printing
for (int i = 0; i < arr.length; i++) {
    System.out.print(arr[i]+" ");
}
```

#### 12. Insertion Sort

#### 13. Merge Sort

#### 14. Quick Sort

#### 15. Heap Sort (Binary Heap)

#### 16. How to Find missing Number on Integer Array of 1 to 100

#### 17. How to Find duplicate Number on Integer Array of 1 to 100

#### 18. HackerRank: Robot class

Question: https://www.luminpdf.com/viewer/5e7a28dec8486d001815a8a3

```
class Robot{
    private int currentX;
    private int currentY;
    private int previousX;
    private int previousY;

    public Robot(){
        currentX = 0;
        currentY = 5;
        previousX = previousY = 0;     
    }
    public Robot(int x, int y) {
        currentX = x;
        currentY = y;
        previousX = previousY = 0;   
    }

    public void moveX(int dx){
        previousX = currentX;
        previousY = currentY; 
        currentX = currentX + dx;
    }

    public void moveY(int dy){
        previousX = currentX;
        previousY = currentY; 
        currentY = currentY + dy;
    }
    
    public void printCurrentCoordinates(){
        System.out.println("Current Position :: " + currentX + " " + currentY );
    }
    
    public void printLastCoordinates(){
        System.out.println("Previous Position :: " + previousX + " " + previousY );
    }
    
    public void printLastMove(){
        if(currentX != previousX) System.out.println("x : " + (currentX-previousX));
        if(currentY != previousY) System.out.println("y : " + (currentY-previousY));
    }
}
```
