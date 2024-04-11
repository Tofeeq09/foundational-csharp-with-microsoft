# Challenge project - Develop foreach and if-elseif-else structures to process array data in `C#`

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/challenge-project-arrays-iteration-selection/5-knowledge-check>

1. **A developer is working on a nested `foreach` structure that iterates through the application's array data. The first array contains the names of 10 geographic regions. The remaining arrays are based on the 10 regions. Each regional array contains the population of cities that have a population over one million. The population values in the regional arrays go from largest to smallest. The application sums the 25 most populated cities in each region. How should the developer ensure that only the 25 largest populations are added to the sum?**

   - `The developer should insert a "marker value" into the population arrays. The "marker value" should be added at index position 25. When the marker value is detected, the application should stop adding values to the sum.`
     > Incorrect. The developer should not modify application data. There are ways to track the number of array elements that have been processed within a `foreach` loop.
   - `The developer should check the index number of the current array element inside the foreach code block. The application should stop adding values to the sum when the index number reaches 25.`
     > Incorrect. A `foreach` loop does not have a mechanism for checking the index number of array elements.
   - `The developer should increment a counter inside the foreach code block. The application should stop adding values to the sum when the counter reaches 25.`
     > **Correct**! The developer should use a counter that increments inside the `foreach` loop.

2. **A developer is working with two other developers to update a collection of applications. The developers will use code comments during the update process. Which of the following describes an appropriate use of code comments?**

   - `When updates are made, the developers use line and block comments to identify each individual code update.`
     > Incorrect. Code comments should not be used to describe individual code lines. In this case, it would be better to summarize changes in a single block comment at the top of the files that contain updates.
   - `When updates are made, the developers leave all existing code comments intact. New comments are added to indicate when old comments no longer apply.`
     > Incorrect. Old comments that no longer apply to the current application can be confusing and should not be retained. A history of the application should be documented in a change log.
   - `When updates are made, the developers summarize changes using block comments.`
     > **Correct**! Using a block comment to summarize the changes implemented during an update is a good use of code comments. A single block comment at the top of the files that contain updates is often sufficient.
