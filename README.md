# Write a function that will take an array as input, sort, and return the array in descending order. For example, if the array is [3,2,7,4,6,9] the result should be [9,7,6,4,3,2].

function sortArrayDescending(arr) {
    return arr.sort((a, b) => b - a);
}


const array = [3, 2, 7, 4, 6, 9];
const sortedArray = sortArrayDescending(array);
console.log(sortedArray); // Outputs: [9, 7, 6, 4, 3, 2]








## Write a function that will take a string as input, check and return if it is palindrome or not. For example, if the string is “madam” the function should return true and if the string is “doctor” it should return false.Write a function that will take a string as input, check and return if it is palindrome or not. For example, if the string is “madam” the function should return true and if the string is “doctor” it should return false.

function isPalindrome(str) {
    const cleaned = str.replace(/[^A-Za-z0-9]/g, '').toLowerCase();
    const reversed = cleaned.split('').reverse().join('');
    return cleaned === reversed;
}


console.log(isPalindrome("madam"));    




# Write a function that will take an array as input and return the sum of the two largest numbers in a n array. For example, in the array [3,7,1,5,11,19] the result would be 30 because 11 and 19 are the largest numbers.

function sumOfTwoLargestNumbers(arr) {
    arr.sort((a, b) => b - a);
    return arr[0] + arr[1];
}

// Example usage:
const array = [3, 7, 1, 5, 11, 19];
const result = sumOfTwoLargestNumbers(array);
console.log(result); // Outputs: 30





# Write a function that will take an array as input and return an array with every missing element from 0 to the highest entry. For example, in an array [3,4,9,1,7,3,2,6] the highest entry is 9, and missing numbers are [0,5,8]


function findMissingElements(arr) {
    // Find the maximum value in the array
    const maxVal = Math.max(...arr);

    // Create an empty array to store missing numbers
    let missingNumbers = [];

    // Check each number from 0 to maxVal to see if it's missing in the array
    for (let i = 0; i <= maxVal; i++) {
        if (!arr.includes(i)) {
            missingNumbers.push(i);
        }
    }

    return missingNumbers;
}

// Example usage:
const array = [3, 4, 9, 1, 7, 3, 2, 6];
const missing = findMissingElements(array);
console.log(missing); // Outputs: [0, 5, 8]




# Write a function that will take an array of numbers and return the number most repeated in the array with how many times it was repeated. For example, if the array is [4,3,5,6,4,7,9,2,4,6,3,4,6,3,4,8,5,1,5] the function should return 4 is repeated 5 times.



function findMostRepeated(arr) {
    const frequency = {};
    let maxCount = 0;
    let mostRepeatedElement = null;

    for (const num of arr) {
        if (frequency[num]) {
            frequency[num]++;
        } else {
            frequency[num] = 1;
        }

        if (frequency[num] > maxCount) {
            maxCount = frequency[num];
            mostRepeatedElement = num;
        }
    }

    return `${mostRepeatedElement} is repeated ${maxCount} times`;
}

// Example usage:
const array = [4, 3, 5, 6, 4, 7, 9, 2, 4, 6, 3, 4, 6, 3, 4, 8, 5, 1, 5];
console.log(findMostRepeated(array));  // Output: 4 is repeated 5 times




# Write a function that will take an array as input, it will rotate the array to the right 1 time and return the rotated array. Rotation of the array means that each element is shifted right by one index. For example, the rotation of array A = [3,8,9,7,6] is [6,3,8,9,7]


function rotateArrayRight(arr) {
    if (arr.length > 0) {
        const lastElement = arr.pop();
        arr.unshift(lastElement);
    }
    return arr;
}

// Example usage:
const array = [3, 8, 9, 7, 6];
const rotatedArray = rotateArrayRight(array);
console.log(rotatedArray); // Outputs: [6, 3, 8, 9, 7]

