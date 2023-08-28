# 🥕 **Kroky Plus** 

**Kroky Plus** is web app for **automatisation** of weekly school snack ordering from [kroky.si](https://www.kroky.si/2016/?mod=register&action=order)
![KrokyPlus](https://github.com/lin-cadez/Kroky-Plus/blob/main/thumbnail.png?raw=true)

##  **💡 Getting the Idea**
I found myself often forgetting to order school snacks for next week so I was left with someting like this:
![Flavorless food](https://github.com/lin-cadez/Kroky-Plus/blob/main/bad_food.jpg?raw=true)

But I knew i could have something like that:
![Delicious food](https://github.com/lin-cadez/Kroky-Plus/blob/main/good_food.png?raw=true)

Something had to be done... So here is **Kroky Plus ➕**

## 🛠️ **The Inner Workings of Kroky Plus**
1. 📝 **Simple Registration Process**: Begin by registering using the credentials provided by Kroky at your school.
    - These credentials allow the algorithm to access your account and gather data on your past orders. ![Image of Registration](https://github.com/lin-cadez/Kroky-Plus/blob/main/register.png?raw=true)

2. 🌟 **Personalized User Area**: Once registered, access your user area to input data that will fine-tune menu recommendations. Share your favorite and least favorite menus, meals, and drinks.
    ![Image of User Area](https://github.com/lin-cadez/Kroky-Plus/blob/main/user_area1.png?raw=true)
![Image of User Area](https://github.com/lin-cadez/Kroky-Plus/blob/main/user_area2.png?raw=true)
![Image of User Area](https://github.com/lin-cadez/Kroky-Plus/blob/main/user_area3.png?raw=true)

3. 💌 **Weekly Confirmation and Selection**: Each week, you'll receive a confirmation email containing the recommended meals.

## 🧠 **The Algorithm Behind Kroky Plus**
Curious about how the algorithm works? Let's dive into the technical aspects:
### 1. **Algorithm Workflow**:
- The algorithm commences by blending past order data, stored as a Firebase dictionary, with your input.
- The steps include:
   1. **Getting the Next Week's Menu**: It retrieves the menu for the upcoming week.
     2. **Iterating Through Days**: The algorithm iterates through each day.
    3. **Analyzing Daily Menus**: It reviews all 10 menus available for a given day.
    4. **Initial Meal Scores**: Each meal starts with a score of 100.
    5. **Considering User Preferences**: The algorithm checks the user's blacklisted and whitelisted meals.
    6. **Adjusting Scores**: If a meal is blacklisted, its score is halved; if whitelisted, it's doubled.
    7. **Comparing to Previous Orders**: It compares these scores to data from previous orders, if available.
    8. **Scoring Based on History**: Meals that appeared frequently in past orders are assigned a score based on the number of times they've been ordered before.
    9. **Incorporating Menu Preferences**: Afterward, the algorithm factors in the menu blacklist and whitelist, adjusting the scores accordingly.
    10. **Accounting for Drink Preferences**: Scores are doubled for preferred drinks and halved for non-preferred drinks.
    11. **Selecting the Top Choice**: Finally, the algorithm sorts the dictionary and selects the item with the highest score.
    12. **Sending Requests and Confirmation**: It makes an API request to the kroky.si server and sends a confirmation email.

### 2. **Refining Data for Enhanced Accuracy**:
- To illustrate, let's use an example menu: 
    ```
    BAKED RICE WITH VEGETABLES, DRINK
    ```

The data refinement process unfolds as follows:
 1. Drink-related terms are omitted for clarity: 
    ```
    BAKED RICE WITH  VEGETABLES
    ```
 2. The menu is tokenized: 
    ```
    [BAKED, RICE, WITH, VEGETABLES]
    ```
 3. Conjunctions are removed: 
    ```
    [BAKED, RICE, VEGETABLES]
    ```
 4. The refined data is compiled into a dictionary stored in the database.
    ![Database](https://github.com/lin-cadez/Kroky-Plus/blob/main/db.png?raw=true)

## 🎨 **A Focus on User Experience Design**
Our design journey aimed to create a seamless experience for users:
- The design, primarily shaped by [Jakecer](https://github.com/jakecernet), is optimized for desktop and potential mobile adaptation.
- Initially, an early prototype featured a drag-and-drop meal selection system (see Early Prototype image below).
- This evolved into a more intuitive model with a user-friendly interface (see Final Design image below).

*Early Prototype*:
![Image of Early Prototype](https://github.com/lin-cadez/Kroky-Plus/blob/main/prot1.png?raw=true)
![Image of Early Prototype](https://github.com/lin-cadez/Kroky-Plus/blob/main/prot2.png?raw=true)

*Final Design*:
![Image of Final Design](https://github.com/lin-cadez/Kroky-Plus/blob/main/final1.png?raw=true)
![Image of Final Design](https://github.com/lin-cadez/Kroky-Plus/blob/main/final%202.png?raw=true)
## 👥 **Team Collaboration and Roles**
For collaboration, we used GitHub Projects.  It's a great application , beacuse it allows you clear and transparent task assignment.
![project](https://github.com/lin-cadez/Kroky-Plus/blob/main/project.png?raw=true)

Our project was a collaboration among three developers:
- Lin Cadez implemented logic 
- Jaka Cernetic was lead designer.
- Maj Mohar taught us the basics of Firebase 

## 🏁 **Summing It Up**

That is all....

*Enjoy delicious school snacks chosen by Kroky Plus! 🥪🎉*

