# DSA-Big-O

## 1. What is the Big O for this?

#### 1) Determine the Big O for the following algorithm: You are sitting in a room with 15 people. You want to find a playmate for your dog, preferably of the same breed. So you want to know if anyone out of the 15 people have the same breed as your dog. You stand up and yell out, who here has a golden retriever and would like to be a playdate for my golden. Someone yells - "I do, be happy to bring him over"
-     **This would be O(1) because regardless of the size of the room, it's a constant response time.**

#### 2) Determine the Big O for the following algorithm: You are sitting in a room with 15 people. You want to find a playmate for your dog who is of the same breed. So you want to know if anyone out of the 15 people have the same breed as your dog. You start with the first person and ask him if he has a golden retriever. He says no, then you ask the next person, and the next, and the next until you find someone who has a golden or there is no one else to ask.
-     **This would be O(n) because the time that it takes to complete the task is dependant on the size of the inputs, its linear.**

## 2. Even or odd
####  What is the Big O of the following algorithm? Explain your answer
```javascript
function isEven(value) {
    if (value % 2 == 0) {
        return true;
    }
    else
        return false;
    }
}
```

-     **This would be O(1) because reqgardless of the input, the function has a constant run time as its not dependent on the inupt.**

## Are you here?
#### What is the Big O of the following algorithm? Explain your answer
```javascript
function areYouHere(arr1, arr2) {
    for (let i = 0; i < arr1.length; i++) {
        const el1 = arr1[i];
        for (let j = 0; j < arr2.length; j++) {
            const el2 = arr2[j];
            if (el1 === el2) return true;
        }
    }
    return false;
}
```

-     **This would be O(n^k) because of the two for loops, it is polynomial time. For loop is a constant time, a nested for loop is          raising that time to another constant unkown power.**

## 4. Doubler
####  What is the Big O of the following algorithm? Explain your answer
```javascript
function doubleArrayValues(array) {
    for (let i = 0; i < array.length; i++) {
        array[i] *= 2;
    }
    return array;
}
```
-     **This would be O(n) because the for loop is a constant time that is linear to the input. **

## 5. Naive search
####  What is the Big O of the following algorithm? Explain your answer
```javascript
function naiveSearch(array, item) {
    for (let i = 0; i < array.length; i++) {
        if (array[i] === item) {
            return i;
        }
    }
} 
```

-     **This would be O(n) because the for loop is a constant time that is linear to the input. **

## 6. Creating pairs:
####  What is the Big O of the following algorithm? Explain your answer
```javascript
function createPairs(arr) {
    for (let i = 0; i < arr.length; i++) {
        for(let j = i + 1; j < arr.length; j++) {
            console.log(arr[i] + ", " +  arr[j] );
        }
    }
}
```

-     **This would be O(n^k) because of the two for loops, it is polynomial time. For loop is a constant time dependent upon the input.
     **A nested for loop is raising that first constant time to another constant unkown power determined by the input.**

## 7. Compute the sequence
####  What does the following algorithm do? What is its runtime complexity? Explain your answer
```javascript
function compute(num) {
    let result = [];
    for (let i = 1; i <= num; i++) {

        if (i === 1) {
            result.push(0);
        }
        else if (i == 2) {
            result.push(1);
        }
        else {
            result.push(result[i - 2] + result[i - 3]);
        }
    }
    return result;
}
```

-     **This would be O(n) because the for loop is a constant time that is linear to the input. **

## 8. An efficient search
####  In this example, we return to the problem of searching using a more sophisticated approach than in naive search, 
####  above. Assume that the input array is always sorted. What is the Big O of the following algorithm? Explain your answer
```javascript
function efficientSearch(array, item) {
    let minIndex = 0;
    let maxIndex = array.length - 1;
    let currentIndex;
    let currentElement;

    while (minIndex <= maxIndex) {
        currentIndex = Math.floor((minIndex + maxIndex) / 2);
        currentElement = array[currentIndex];

        if (currentElement < item) {
            minIndex = currentIndex + 1;
        }
        else if (currentElement > item) {
            maxIndex = currentIndex - 1;
        }
        else {
            return currentIndex;
        }
    }
    return -1;
}
```

-     **This would be O(log(n)) because it's cutting the problem into half each iteration. **

## 9. Random element
####  What is the Big O of the following algorithm? Explain your answer
```javascript
function findRandomElement(arr) {
    return arr[Math.floor(Math.random() * arr.length)];
}
```

-     **This would be O(1) because regardless of the size of the array the function has a constant execution time since it always
      **accessing a single variable from the array. **

## 10. What Am I?
####  What does the following algorithm do? What is the Big O of the following algorithm? Explain your answer.
```javascript
function isWhat(n) {
    if (n < 2 || n % 1 != 0) {
        return false;
    }
    for (let i = 2; i < n; ++i) {
        if (n % i == 0) return false;
    }
    return true;
}
```
-     **This would be O(n) because the for loop is a constant time that is linear to the input. **

## 11. Tower of Hanoi
####  The Tower of Hanoi is a very famous mathematical puzzle (some call it game!). This is how it goes:

######   There are three rods and a number of disks of different sizes which can slide onto any rod. The puzzle starts with the disks neatly stacked in ascending order of size on one rod, the smallest disk at the top (making a conical shape). The other two rods are empty to begin with.
######   The goal of the puzzle is to move the entire stack of rods to another rod (can't be the original rod where it was stacked before) where it will be stacked in the ascending order as well. This should be done obeying the following rules: i) Only one disk may be moved at a time ii) Each move consists of taking the upper disk from one of the rods and sliding it onto another rod, on top of the other disks that may already be present on that rod. iii) A larger disk may not placed on top of a smaller disk
######   Input:

######   Rod A	           Rod B	           Rod C
######   ----		
######   ---------		
######   -------------		
######   Output:

######   Rod A	           Rod B	           Rod C
######                                       ----
######                                       ---------
######                                       -------------

####  Derive an algorithm to solve the Tower of Hanoi puzzle.
####  Implement your algorithm using recursion. Your program should display each movement of the disk from one rod to another.
####  If you are given 5 disks, how do the rods look like after 7 recursive calls?
####  How many moves are needed to complete the puzzle with 3 disks? with 4 disks? with 5 disks?
####  What is the runtime of your algorithm?









