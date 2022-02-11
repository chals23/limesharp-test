# Limesharp Developer Test

Please, **don't fork this repo**, clone it or download it locally and then commit changes after each task into a new repo of your own, and send us the link. We will get back to you shortly. 

Languages accepted: Javascript or PHP. 

### Task 1: 
Make this work (repeat 3 times the contents of an array):
```javascript
repeat([1,2,3]) //[1,2,3,1,2,3,1,2,3]
```
Your solution:

```javascript
const repeat = (content) => content.concat(content, content);
```

###### If we type in our console your function and repeat([1,2,3]) then the result should be [1,2,3,1,2,3,1,2,3] 

### Task 2:
Make this work (no vowels, lowercase except the first letter):
```javascript
reformat("liMeSHArp DeveLoper TEST") //Lmshrp dvlpr tst
```
Your solution:

```javascript
const filtered = (text) => text.replace(/[aeiou]/gi,'').toLowerCase().replace(/(^[a-z])/, match => match.toUpperCase());

```

###### If we type in our console your function and reformat("liMeSHArp DeveLoper TEST") then the result should be Lmshrp dvlpr tst


### Task 3 (optional, for bonus points):
Make this work (without using any built in functions, only a `for` loop, return the next binary number in a string or as an array)
```javascript
next_binary_number([1,0]) // [1,1]

// possible test cases:
// [1,0] => [1,1]
// [1,1] => [1,0,0]
// [1,1,0] => [1,1,1]
// .......
// [1,0,0,0,0,0,0,0,0,1] => [1,0,0,0,0,0,0,0,1,0]
```
Your solution:

```javascript
const next_binary_number = (binary) => {
  let carry = 1;
  for (const index = binary.length - 1; index > -1; index--){

    const current = binary[index] + carry;

    carry = current - 1;
    current = current - carry * 2;
    binary.splice(index, 1, current);

    if (!carry) {
    	break;
    }
  }
  if (carry === 1) {
  	binary.unshift(1);
  }

  return binary;
}
//TBH: Founded a solution for this task and reformated on my own, as don't know how binary sum works before (now I do), still count as bonus points? :D
```

###### If we type in our console your function and next_binary_number([1,0,0,0,0,0,0,0,0,1]) then the result should look like 1,0,0,0,0,0,0,0,1,0 (or as an array).

---

If you get invited to the first interview read the "What to expect.md" file.