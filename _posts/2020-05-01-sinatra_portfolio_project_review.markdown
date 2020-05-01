---
layout: post
title:      "Sinatra Portfolio Project review"
date:       2020-05-01 19:38:32 -0400
permalink:  sinatra_portfolio_project_review
---


Working on my Sinatra Portfolio project has been an amazing experience with lots of ups and downs, but ultimately, I have learned so much and I couldn't ask for more.

I had to create the applcation from scratch, and I started the project off by installing the gem called "Corneal". This gem was crucial to start off strong. I find it difficult to get started and having everything set before I even start to code. Corneal is a Sinatra App Generator that makes starting your project much easier with the necessary file structure needed to get started.

The application I created is called "Top Games." Users can sign up and create a list with a list name and their top five games. The first thing I had to do was create the associations between the user and games. A user can have many games and a game belongs to a user.

```
class User < ActiveRecord::Base
    has_many :games
end
```

and

```
class Game < ActiveRecord::Base
    belongs_to :user
end
```

Afterwards, I went right ahead and created tables for both user and games with the following schema.

```
ActiveRecord::Schema.define(version: 20200426162239) do

  create_table "games", force: :cascade do |t|
    t.string  "first_game"
    t.string  "second_game"
    t.string  "third_game"
    t.string  "fourth_game"
    t.string  "fifth_game"
    t.integer "user_id"
    t.string  "list_name"
  end

  create_table "users", force: :cascade do |t|
    t.string "username"
    t.string "email"
    t.string "password_digest"
  end

end
```

Now that this is done, I needed to go ahead and set up the accounts security. The bycrpt gem helps with that. This gem provides you with the has_secure_password encrypts the password and generates a password_digest, hence, why I had to include password_digest in the schema I showed above. I then put my has_secure_password in my user.rb.

```
class User < ActiveRecord::Base
    has_secure_password
    has_many :games
end
```

After applying this, I needed to create the helpers class and apply the two very useful methods that will help with authentication and making sure to see if the user is logged in or not.

```
class Helpers

    def self.current_user(session)
        @user = User.find_by_id(session[:user_id])
    end

    def self.is_logged_in?(session)
        !!session[:user_id]
    end
end
```

The Helpers class was very useful and made things a lot easier to keep track of the user. This now allowed me to move on to work on my ApplicationController. I can now get started on creating my routes and erb files. When creating my routes, I had to make sure that the user would be logged in and if not, redirect them to the login screen. 

This project was a lot of fun and I am very excited to take on rails next.



