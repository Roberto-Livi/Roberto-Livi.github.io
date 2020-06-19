---
layout: post
title:      "Rails Portfolio Project"
date:       2020-06-19 15:44:24 -0400
permalink:  rails_portfolio_project
---


Creating my very first Ruby on Rails application has been an amazing experience for me. It was really fulfilling to integrate everything that I have learned to create an application that I thought of creating for a while. My application I created is called "Code Folio." I wanted to create a social media application for Software Engineers, hence the name of the app. Some notable features of this app consists of login, registration, search bar, and a follow feature.

**Getting Started**

I started out planning the tables that I needed. I created a Users, Posts, and Comments table to start with their following elements. I then went ahead and created their models with their associations.

User
- has_many :posts
- has_many :comments, through: :posts
- validates :username, uniqueness: true
- validates :password, length: { in: 5..30 }

Post
-  has_many :comments
-  has_many :users, through: :comments

Comments
- belongs_to :user
- belongs_to :post
- validates :content, presence: true

I added in some validations for both the user and comments. I wanted the username to be unique and for the password length to be between five and thirty characters.

With this preparation, I then created controllers for each with their appropriate action routes, and defined these routes in routes.rb. 

Adding in Bcrypt, so I can integrate has_secure_password into my User model to autheticate the user was a must. 


**Middle of the project**

There were a lot of twists and turns throughout the project and felt like each error that I came across was a good thing. This is because I know that if I can get through it, I will come out as a better developer. 

Taking breaks is important.

For example, I thought it was going to be nearly impossible to display all the posts from the users that you are following, starting from the most recent one, on the users index page. I took a 10 minute break from my project and sat down to relax a little. All of a sudden I came up with an idea to make that happen. I immediately got back up and started typing and I got it to work with the following code:

```
<% @posts.reverse.each do |post| %>
            <% if user = current_user.following.find_by(:id => post.user_id) %>
            <p>
                <%= link_to user.username, user_path(user), :style => "background-color: deepskyblue;" %>

                <strong><%= post.title %></strong>
                <%= post.content %>
            </p>
            <% end %>
```

When you take breaks, your mind starts to clear up and you will be able to think more clearly. This has happened to me multiple times when working on this project.


**Conclusion**

Many of the things that weren't sticking to me throughout the lessons, started to make sense as I was working on this project. This is why it's good practice to work on projects. I am really grateful for this project, and will continue to do more as I strive to become a better programmer and problem solver every day.



