This react project will implement and visualize the sorting algorithms such as, Merge sort, Quick sort, Heap sort and Bubble sort

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## MERGE sort 
Is a 'Divide and Conquer' algoithm. It divides the array in halves, sort each halves and merge the two sorted halves together. The Merge() function is used 
for merging the two halves. The Merge(arr, l, m) assumes the array in l and l+1 are sorted and combine them together. 
Time complexity: O(n*logn).

## BUBBLE sort: 
A "naive" sorting algorithm that simply walks through the array, every time a particular element is out of order, it will swapped to the right position. The algorithm will continue walking through the array until all elements are sorted. This is a very slow algorithm, as time complexity is: O(n^2) with n being the number of elements within the array.
The algorithm has two for loops, i < length and j < length - 1

## QUICK sort: 
Quick sort algorithm generally take an array and pick some element insdie it to be a "Pivot" element randomly. After that, the algorithm will walk through the array and swap element around, so that any element that is lesser than the pivot would come before the pivot. On the other hand, any element that is greater than the pivot would come after it in the array. This way, it would create a natural division within the array, and repeat this steps for the left portion and right portion of the array. We would continue until all the element has been sorted.

Time complexity: Depends on where the pivot element is, the time complexity would be improved!
 ===> Average case: O(nlogn)
 ===> Worst case: O(n^2) : if the pivot element is the first element in the array

 # Easiest Implementation of QUICK sort (Pivot is the last element in the array)
  if (origArray.length <= 1) { 
		return origArray;
	} else {

		var left = [];
		var right = [];
		var newArray = [];
		var pivot = origArray.pop();
		var length = origArray.length;

		for (var i = 0; i < length; i++) {
			if (origArray[i] <= pivot) {
				left.push(origArray[i]);
			} else {
				right.push(origArray[i]);
			}
		}

		return newArray.concat(getQuickSort(left), pivot, getQuickSort(right));
	}

## HEAP sort: 
**Heap: Ordered binary tree
**max heap: parent > child
**Build Max Heap: creates a max heap from unsorted array
**Heapify: similar to build-max-heap, but assumes part of the array is already sorted.

Steps: 1. Create a max heap => to find the largest item in the array
	   2. Remove largest item 
	   3. Place item in a sorted partition

Example array: 2 8 5 3 9 1 

We will represent the array as a binary tree
=> 			2										9
		8		 5   Build Max heap -> 			8		 5	  -> now we know the largest number to be 9, we will swap 9 with the last element in the array, then removes 9 from the tree and 
	3		9	1							3		2	1		considered it sorted. Repeat the process by keep building the max heap and swapping out the largest element with the last element in unsorted 
																partition of the array.

====> Time complexity: O(nlogn); build max heap: O(n), heapify: O(logn),called n-1 times


## Insertion Sort: 
Not the best sorting algorithm in term of complexity, but it has better application than selection sort. 
The algorithm will split the current array into two sub array, which is "sorted" and "unsorted". The sorted array will is empty at first and the algorithm will compare each other sequentially and then arrange simultaneously in some particular order. 

The implementation in this source code will use two pointers called, Index anad Hole. The index, denoted as i, will look at each index in the array, and the hole will hold the element that will be rearranged or 'inserted' into the sorted array part correctly.

Time Complexity: O(n)

Javascript implementation:

    //Looping through the array to sort elements starting from index 0:
    for(let i = 1; i < array.length; i++)
    {
        //variables to hold the index and value at current index.
        let value = array[i];
        let hole = i;
        //while loop to compare and swap element:
        while(hole > 0 && array[hole - 1] > value)
        {
            //swap the element, larger element will go after and smaller will go first:
            array[hole] = array[hole - 1];
            hole--;

        }
        // set the elemenet at hole to become the value
        array[hole] = value

    }

    return array;


## Selection Sort: 

The algorithm will splits the array into two parts, a sorted and unsorted part. The algorithm will sort an array by repeatedly finding the smallest element from the unsorted part.
In every iteration of the selection sort, the smallest element from the unsoted part of the sub array is picked and moved to the sorted array

Time complexity: O(n^2) 

Code implementation: 
    let length = array.length
    //loop through the array until n-2 (n is the length of the array)
    for(let i = 0; i < length - 1; i++)
    {
        //set the smallest element to be at the current index of the loop
        let indexOfMin = i;
        //loop through the array again to match the smallest element with its neighbors
        for(let j = i +1; j < length; j++)
        {
            //if the neighbor element is lesser than the smallest element, then swap the index of the 
            if(array[j] < array[indexOfMin])
            {
                //smallest element to be the neighbor
                indexOfMin = j;
            }
        }

        let temp = array[i];
        array[i] = array[indexOfMin];
        array[indexOfMin] = temp;
    }
    return array;



## Animation


## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.<br />
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br />
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.<br />
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.<br />
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br />
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: https://facebook.github.io/create-react-app/docs/code-splitting

### Analyzing the Bundle Size

This section has moved here: https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size

### Making a Progressive Web App

This section has moved here: https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app

### Advanced Configuration

This section has moved here: https://facebook.github.io/create-react-app/docs/advanced-configuration

### Deployment

This section has moved here: https://facebook.github.io/create-react-app/docs/deployment

### `npm run build` fails to minify

This section has moved here: https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify
