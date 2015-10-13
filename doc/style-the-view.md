## Style the view

Since we are focusing on Ruby and Rails here, we are going to use a CSS-Framework to provide us with some basic styling. We are using SemanticUI by adding the following to our `Gemfile`:

```
gem 'semantic-ui-sass', github: 'doabit/semantic-ui-sass'
```

To include the stylesheets and javascripts that make SemanticUI work, we need to `require` them.

Add this to `app/assets/stylesheets/application.css` in to the comment-block at the top before the `*/`:

```
*= require semantic-ui
```

And add the javascript to `app/assets/javascripts/application.js` also in the first comment-block, best before `require_tree .`:

```
//= require semantic-ui
```

To finish up our styling here is a snippet to add to `application.css`:

```
body { padding: 2em 35%; }
.input { width: 100%; }
ul { margin: 2em 0; padding: 0;}
li { list-style: none; }
```

This will make our Todo-list look good once we add more to our template.

** During your development in Rails, there will be times where you will want to provide some functionality but either you don't know how to do that or you don't want to implement it on your own as there probably is already 'something out there' and you don't want to reinvent the wheel. These developments which you might need (user authentication, message system, geolocation, ...) are called Ruby Gems. These are Ruby software packages. Your gemfile is a list of all gems that you want to include in your project. It is used with bundler (which is also a gem) to install, update, remove and otherwise manage your gems.

💾 [Add SemanticUI](https://github.com/bastilian/todo-application/commit/b5867646342b9ecfe2abc8f5dae77df48df8ca38)
