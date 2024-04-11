# Guided project - Develop foreach and if-elseif-else structures to process array data in `C#`

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/guided-project-arrays-iteration-selection/6-knowledge-check>

1. **A developer writes an application that uses a `foreach` loop to iterate through an array containing 20 elements. After the application is complete, the developer learns that the array must be updated to include 40 elements. The application needs to examine all 40 array elements. Which of the following items describes the required code update?**

   - `Create a second foreach loop that iterates through the additional items.`
     > Incorrect. This will cause the array elements to be processed twice.
   - `No changes are required to the foreach loop.`
     > **Correct**! A `foreach` loop will iterate through all of the elements in an array.
   - `Place the original foreach loop inside the code block of a second foreach loop that iterates twice.`
     > Incorrect. This will cause the array elements to be processed twice.

2. **A developer is working on a nested `foreach` structure that iterates through all of an application's data arrays. The first array contains the names of locations where water samples were collected. The remaining arrays contain the test results for the samples collected from each named location. Which of the following statements about how the arrays should be processed is correct?**

   - `Each of the arrays containing samples can be processed by the outer loop, the inner loop will be used to verify the location.`
     > Incorrect. The outer `foreach` loop can only process one array, so it can't process each of the arrays containing samples.
   - `The order in which the arrays are processed doesn't matter since the application has to process all of the data.`
     > Incorrect. The relationship between outer and inner `foreach` loops is critical. The application won't be able to process all of the array data that's described in this scenario if the nested `foreach` structure isn't established correctly.
   - `The outer loop must process the array containing locations, the inner loop must process the arrays containing samples.`
     > **Correct**! The outer loop will iterate through the locations. The code block of the outer loop will be used to select the samples array for each location, and then process the sample in the inner `foreach` loop.
