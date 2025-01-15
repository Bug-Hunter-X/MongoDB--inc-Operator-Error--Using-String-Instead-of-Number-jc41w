# MongoDB $inc Operator Error

This repository demonstrates a common error when using the `$inc` operator in MongoDB update operations: using a string value instead of a numeric value. This results in the increment failing and potentially unexpected data changes.

## Bug
The bug is in the use of `$inc` in the `updateOne` method.  The value being incremented ('1') is passed as a string.  This will not perform the intended increment.  The correct approach is to provide a numeric value. 

## Solution
The correct usage is to provide the numeric value directly to the `$inc` operator. For example: `{$inc: {field: 1}}` will properly increment the field.

## How to Reproduce
1.  Set up a MongoDB instance.
2. Create a collection named 'myCollection'.
3. Insert a document with an _id of 1 and a 'field' with an initial value.
4. Run the code in `bug.js`. The field will not be incremented correctly.
5. Run the code in `bugSolution.js`. The field will be correctly incremented.
