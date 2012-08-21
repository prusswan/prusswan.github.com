---
wordpress_id: RB-7
layout: post
title: Two tips on Bundler
---

Quite often, `bundle install` does not work when offline (unless all the specific-version gems happen to be installed already). The solution is actually [`bundle install --local`](http://gembundler.com/man/bundle-install.1.html), but you may ask: why haven't I seen it in the console help pages ever?

The reason is that, it is still an open [feature request](https://github.com/carlhuda/bundler/issues/591), with the current workaround as follows:

{% highlight bash %}
# execute this in the installed location of the bundler gem
cd man
mv gemfile.5{.ronn,}
for f in *.ronn; do cp `basename $f .ronn`{.ronn,.1}; done
{% endhighlight %}

With that and `gem install gem-man`, `gem man bundle` will bring up the list of the man pages for offline perusal.
