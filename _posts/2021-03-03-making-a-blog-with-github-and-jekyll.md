---
layout: post
title: "Making a blog with Github and Jekyll"
date: 2021-03-03 18:05:17 -0800
tags: [Learning, Github, Jekyll]
categories: [Learning, Github, Jekyll]
---

I recently finished up a variety of online courses about React and am getting
ready to start working on a Japanese typing game. Over the past month, though,
I've come to realize that it can be hard to feel like I'm making progress.
After all - there's no one there to set deadlines or check-ins other than me.
I've also come to realize that I learn more when I write things down.

Because of that, I decided to make a simple blog to document what I'm doing
and why. I remembered seeing something about Github pages awhile back and
figured that it would be nicer to just host something on Github rather than
making a Wordpress site or paying to host something fancy.

## Github pages

The first thing I did was go to the [Github pages](https://pages.github.com/)
site and follow their instructions for making a page. While I enjoyed the
simplicity of it, there were a few things I was a bit annoyed by. First off,
the instructions don't mention that if you don't initialize the repo that
you're then going to have to do some setup work in between the steps.
Furthermore, it's not clear how long it takes to "deploy" or what the status
of deploying it is. I originally thought I messed something up as the site
was totally different than what I put in my `index.html` file.

Fortunately, the site did come up - but then I was left wondering - how do
you turn this into a blog? Surely I'm not going to just make a giant file
that I'll constantly edit, right?

## Jekyll

After searching around online, I found a few posts that talked about
[Jekyll](https://jekyllrb.com/). I tried following the instructions on the
Jekyll website and, unfortunately, they didn't work at all. Their site makes
it seem like all you need to do is run `gem install bundler jekyll` and things
will just work - but when I then went to run `jekyll` it gave me an error
about the command not being found.

I then went to the [Mac OS Install Guide](https://jekyllrb.com/docs/installation/macos/)
and started going through that. I installed ruby with Homebrew
(`brew install ruby`) and then I added Ruby to my path
`echo 'export PATH="/usr/local/opt/ruby/bin:$PATH"' >> ~/.zshrc`
which worked. Unfortunately, I later found out that the Github pages gem is
running with `Ruby 2.7.x` and they [don't support Ruby 3.0.0](https://github.com/github/pages-gem/issues/752#issuecomment-764758292)
so you either need to specify the right version of Ruby to install (which the
instructions don't include) or you need to figure out what's going wrong when
you try and start things up. I found out that `webrick` is no longer bundled
with Ruby and you'll get errors around that unless you manually install that
after the fact ([github issue](https://github.com/github/pages-gem/issues/752))

The instructions then say to install `bundler` and `jekyll` using the command
`gem install --user-install bundler jekyll` - but this, again, did not work
for me. Even after following their instructions to echo a new PATH into my
zshrc file pointing at the Ruby gems:
`echo 'export PATH="$HOME/.gem/ruby/X.X.0/bin:$PATH"' >> ~/.zshrc`
I still was unable to run `bundle` correctly. Fortunately, I did notice in
my error messages it mentioned something about needed to add
`/Users/mikesol/.local/share/gem/ruby/3.0.0/bin:$PATH` to my PATH in order for
the gems to appear correctly - and adding that worked. I was _finally_ able
to run `bundle exec jekyll serve`.

By this point, though, I was fairly fed up with following along on their site
and wanted to find an easier way to do things.

## Jekyll Now

I searched around online for a bit and stumbled across the [Jekyll Now](https://github.com/barryclark/jekyll-now)
repo. It seemed like exactly what I needed! I could just fork that and get a
site up and running right away. I did that and it worked! Unfortunately, I then
started to realize some issues...

- The repo hadn't been updated in years
- There were over 100 open issues - many of which had solutions and proposed PRs but
  no response from the creator.
- Things like displaying code in blog posts were broken.
- There was no way to see tags or categories for posts.
- You had to give up control of some of the core parts of Jekyll (such as having a
  Gemfile and adding new gems)
- Forking a repo means it doesn't track changes as git commits - which was something
  I liked the idea of.

In looking through the pull requests and issues, I did find another repo that showed
more promise, though!

## Reverie

Someone posted as a comment that they forked `Jekyll-Now` and made something very
similar but with a few key changes. Furthermore, it was actually actively supported
and fixed a lot of the issues. That repo was [Reverie](https://github.com/amitmerchant1990/reverie)

It had the same option of forking it - but I decided to try and copy the core files
into my newly generated Jekyll code base instead (so I didn't have to deal with the
problems of forking a repo).

I really liked Reverie for the most part, but I found a few key things I didn't like:

- I didn't like how _everything_ was cenetered on it.
- I didn't like the search page
- I didn't like the categories page
- I didn't like the fact that the blog posts all included the author's name.
- I didn't like the way excerpts were done. For instance, if you started your post
  with a section like `## Some cool section name` - then the excerpt would _just_ be that.

I ended up digging in to a lot of the Sass and other things and trying my best to
fix what I could with my limited knowledge of this stuff. I was able to fix most of
the issues to some degree (although the categories page and excerpts are still
problematic).

That being said - it was a way nicer experience than before and I'll probably stick
with it like this for awhile.

## Github pages themes

One thing I noticed after the fact was that you can change the theme on Github via
a "theme selector". Unfortunately, if you do do that - [your entire site breaks](https://github.com/github/pages-gem/issues/416). This
is because various themes expect certain layouts or keys and you'd have to update
your site to reflect that (and there are naturally no instructions for that).

## A script for generating posts

One annoying part about making new posts with Jekyll is you have to remember to name
and set up the post properly. I didn't want to have to check the date and properly
write things each time - so I searched around for a script that would help with this.

Fortunately, I found [this gist](https://gist.github.com/aamnah/f89fca7906f66f6f6a12#gistcomment-3243700) that had a really clean and simple script
for doing just that. I made some minor tweaks to better suit my needs and then stuck
it in this repo and used it to make this post ^.^

## Conclusions / Going Forward

This was certainly way more work than I was expecting to get a simple blog set up.
However, now that it's set up, I may just leave it like this for awhile. After all,
I don't really expect many people to read many of these posts and I don't need
something gorgeous to write down and learn from.

In the future I may decide to try out a different site - but the security / simplicity
of this is pretty cool.

Have you set up a blog with Github pages? Did you use Jekyll? How as your experience?
I'd love to hear about it ^.^
