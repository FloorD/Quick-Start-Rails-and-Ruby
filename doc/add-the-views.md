## Add the views

If your server is started and you go to [http://DOCKER_IP:3000/todos](http://DOCKER_IP:3000/todos), it will tell you that the action is missing. We will need to fix this by adding the action.

First, what do we want to display here? The "index"-action is primarily used for displaying a list, in this case a list of todos. The first thing we will do then is grab all Todos from our database in the `index`-action.

Open the file `app/controllers/todos_controller.rb`, you should see the following:

```
class TodosController < ApplicationController
end
```

This creates a new Controller class for us in which we can put in our action. In between the above lines add this:

```
  def index
    @todos = Todo.all
  end
```

The above code defines a new method for the Controller Object, or in this context called "action". When it is executed (by going to `/todos` in the browser) it will define a variable which asks the Todo-Model for **all** Todos in the database. The variable will be passed to the View as well, you'll see that soon.

Once you've saved the file and refreshed the page in the browser, you'll see another error, but that's ok. Rails will always try to tell you what is wrong in a way so that you can fix them. This error should tell you that the **Template is missing**, so let's add one. For this create a new file called "index.html.erb" under `app/views/todos`.

You just created a template! Notice the file ending "erb", that tells Rails that this is an ERB-template, which allows you to run Ruby to make your HTML "dynamic", meaning if something in the database changes it changes the HTML.

 * If you want to run Ruby code in your template you wrap (embed) it in `<% ... %>`
 * If you want to display something from Ruby use `<%= ... %>`

First we want to display how many Todos we have. So we ask the `@todos` variable what size it has and show that:

```
<%= @todos.size %>
```

Add this to the template, save it and refresh the page. You should see a number on the page - most likely a "0" - since we have not yet added any todos. Next, let's show the todos in a unordered-list (`<ul>`), for when we have added some.

We are going over each todo in `@todos` and display the description of it. The code you'd write for that would look as follows:

```
<ul>
  <% @todos.each do | todo | %>
    <li><%= todo.description %></li>
  <% end %>
</ul>
```

The page in the browser might still look empty, but we are now all set and ready to implement adding todos!

💾 [Add Todos index view](https://github.com/bastilian/todo-application/commit/bc70de12eabebf5a639d68791bb74f0f76e56d0d)
