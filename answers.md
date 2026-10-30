Part 1: Why does priceRange belong in the Model?
Price is a data point that indicates the cost level of a restaurant. It's in the Model file because it functions as a data set that the controller will pull from as well as the rules that use that data.

Part 6:
1. What problem does MVC help solve?
By separating the data, user interface, and controlling logic, you ensure that the data management and UI can evolve separately without breaking each other. For example, I'm able to add price points without touching the Controller.

2. Why should the Controller not contain the rule restaurant.rating >=4.5?
Because the Controller only responds to what the user does, connecting the data (Model) to the interface (View). The Model doesn't just contain the data, but the rules on how to handle said data.

3. If cards were replaced with a table, which component would change the most?
The View: It contains the card functionality, so that would be where I'd change the formatting. The Model still holds the same data and the Controller can still pass the data along. 

4. Does MVC require three separate JavaScript files?
No, it is not a file-system constraint, but an architectural concept. It's just one way to organize your files by job, but using adequate spacing and labeling through comments, you can organize it all within one JavaScript file.  

5. If data came from a REST API, which component should manage it?
The Model. Its job is to host the dataset.The View and Controller wouldn't need to change, since thay don't care where the data comes from.

MVC Detective:
The code is trying to do two jobs at once: the filtering and the data handoff. It still works, but if the rule changes and needs to be filtered differently, your team, or even you, could be looking in the wrong file for the fix. The Model should contain the filtering logic, because that is it's job.  

showTopRatedButton.addEventListener("click", function () {
      const restaurants = restaurantModel.getTopRatedRestaurants();
      restaurantView.displayRestaurants(restaurants);
    });

 