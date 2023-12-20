# Analysis of code complexity before and after refactoring

We are going to analyse both the temporal and spatial complexity of the codes in order to deduce a probable improvement
after the refactor.

### <u>Before the refactor :</u>

1. It only defines boolean variables and a multi-line string, Therefore, this code snippet is considered to be
   constant <br>
   <u>Time complexity:</u> O(1) <br>
   <u>Space complexity:</u> O(1)

```vim
  ricePresent: false,
  riceCooked: false,
  steamingInProgress: false,
  heatingInProgress: false,
```

2. <u>Time complexity:</u> O(1) Constant number of operation <br>
   <u>Space complexity:</u> O(1) No additionnal space grows with the size of the input.

```javascript
 addRice(); cookRice(); keepWarm(); removeRice();
```

3. <u>Time complexity:</u> O(n) where n is the value of the input parameter ms. This is because the code uses a while loop that runs until the difference between the current time and the start time is equal to or greater than ms. In the worst case, the loop will iterate n times, resulting in a linear time complexity. <br>
   <u>Space complexity:</u> O(1) No additionnal space grows with the size of the input.

```javascript
 steam(); delaySync();
```

4. <u>Time complexity:</u> O(n) n is the number of iterations in the while loop. This is because the code will continue to loop until the condition is false, and the number of iterations depends on the user's input. <br>
   <u>Space complexity:</u> O(1) No additionnal space grows with the size of the input. The only variables used are "input", "condition", and "choice", which all have constant space requirements.

```javascript
 simulateRiceCooker();
```

### <u>After the refactor :</u>

1. It only defines boolean variables and a multi-line string, Therefore, this code snippet is considered to be
   constant <br>
   <u>Time complexity:</u> O(1) <br>
   <u>Space complexity:</u> O(1)

```vim
  ricePresent: false,
  riceCooked: false,
  steamingInProgress: false,
  heatingInProgress: false,
```

2. <u>Time complexity:</u> O(1) Constant number of operation <br>
   <u>Space complexity:</u> O(1) No additionnal space grows with the size of the input.

```javascript
 addRice(); cookRice(); keepWarm(); removeRice();
```

3. #### It was still possible to refactor the function `delaySync()` to improve complexity. <br>
   <u>Time complexity:</u> O(n) where n is the value of the input parameter ms. This is because the code uses a while loop that runs until the difference between the current time and the start time is equal to or greater than ms. In the worst case, the loop will iterate n times, resulting in a linear time complexity. <br>
   <u>Space complexity:</u> O(1) No additionnal space grows with the size of the input.

```javascript
 steam(); delaySync();
```

4. <u>Time complexity:</u> O(1) The switch statement inside the loop has constant time complexity for each case, as it performs a single operation for each case. Therefore, the overall time complexity of the code is constant. <br>
   <u>Space complexity:</u> O(1) No additionnal space grows with the size of the input. The only variable used is "choice", which stores the user's input, and it only takes up a constant amount of space.

```javascript
 simulateRiceCooker();
```