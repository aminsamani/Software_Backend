We want to design a simple Django application using DRF (Django Rest Framework) where users can view a list of articles and rate them. Each article consists of a title and text. Design the following views:

1. Displaying a List of Articles:
    In this view, the title of the article, the number of users who have rated the article, and the average rating should be displayed. Assume that the number of ratings is high! If a user has rated the article, their rating should be displayed.


2. Rating Articles by Users:
    Users submit a number between 0 and 5 as their rating for an article. Each user should be able to rate an article only once. If a user submits a rating again, the previous rating should be updated. The ability to remove a rating is not required.

Consider designing these two views, along with the models, and other related components. Keep in mind the conditions of a real production product. You can disregard other details and consider the simplest cases. For example, user profiles, and so on..."