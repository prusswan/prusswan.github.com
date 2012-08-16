---
wordpress_id: RB-334
layout: post
title: Review&#58; The Rails View - Chapter 1
---

Since I was working a lot on views and getting frustrated by all that mangled code I have written, I thought this would be a useful read and a good exercise as well: I plan to convert the book's code to haml as I go along. This is probably the leading, if not only book on Rails views in the market now, and is still fairly up-to-date.

Chapter 1 is about layouts and introduces several tricks on proper organization, browser compatibility and relating all that to HTML5 and CSS3. The code generally works as expected, with just a few issues like the missing <code>Gemfile.lock</code> file, which will cause problems to those using Devise for the first time as the latest gem version 2.x (which will be fetched by bundle install) no longer works with the code. Another issue is that the examples mentioned are not always complete with the templates, like on page 28:

{% highlight erb %}
<%= render @project.designers %>
{% endhighlight %}

which calls for a missing <code>designer/_designer.html.erb</code> template when the page is rendered. I doubt it will kill the author to add a placeholder for it, so I suppose this is just an unfortunate oversight.

For the breadcrumbs section (page 35), the code is working but the book fails to provide a link or an indication to the actual link to the permissions view which illustrates the breadcrumbs in action, and there's no link to it from within the site either. I suppose the author made the decision to omit the CRUD code for the controllers, so the reader will have to possess at least some knowledge of rails routes for all this to make sense. There's also a typo (<code>edit_creations_path</code> should be <code>edit_creation_path</code>).

Edit: the path is <code>permissions_creation_path(creation)</code>, or <code>/creations/:id/permissions</code>

While I am not expecting a complete spoonfeeding, it is clear that the author did spend considerable effort on the example code: the Devise installation has the login stubbed out so that layout can be shown as it is without requiring any login on the user's part beyond <code>rails s</code>, there's also seed data provided for the various models used (the seed data isn't really used in Chapter 1 however, and the missing crud operations do not help), the relatively trivial effort needed to work in the omissions would only have made it more complete.
