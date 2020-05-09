---
title:  "What it takes to build your own website!"
last_modified_at: 2020-05-09T17:38:00-04:00
---
So after a long time contemplating how to build an effective portfolio I finally decided on building my own website using github pages. It definitely wasn't easy sailing through this process. I had to scratch my head over a ton of stuff to figure out a way to build this website through a repository on github.

Disclaimer: Before you read on, know that if you embark on this journey without any prior knowledge of html, css or ruby, it will take time to get a hang of things. You HAVE to be patient in order to make this work.

If you don't care about themes in general, building a website on github is fairly easy. However, if you're like me (who wants customizable formats) you'll have to take the longer route.

Before I get onto the technical aspects, let me tell you my long path to this stage:

1. I first started a blog on wordpress back in 2016. I tried to make use of it, but it barely took off. I even tried to revive it in 2019, but to no avail. I just couldn't make it my own I guess even with all the options it provided. The other big struggle I had was when I had blogs with pictures and a lot of text which was making the process a nightmare.

2. I also thought about writing medium articles and showcasing everything through that platform, but I just didn't like the idea that someone would have to probably pay to even view my stuff. That essentially defeats two things in my opinion: (i) I won't be able to market myself the way I truly wish to and (ii) I am a strong believer in the open source community and it just didn't feel right. Although as I progress in my career in the field of Data Science, I would contribute to the Medium platform in some form, but right now it just feels like I need to give back to this growing community, especially since most of the stuff I've ever ended up learning was because of this open source community.

3. Last thing I tried (which was also fairly recent) was creating a website on wix. As it turns out, having your name exclusively in the url is pretty cool as opposed to having a ".wix.com" or a ".wordpress.com" at the end of your website. Moreover, the amount of options available overwhelmed me to the point that I just didn't feel like it's "MY WEBSITE" anymore even with all the customizations available.

At the end of the day, I did want options to customize my website, but also wanted to keep it simple. I finally resorted to github pages and felt like it's a good learning process too.

Now, I made a lot of mistakes. By 'a lot' I mean A LOT! It was a freaking nightmare initially. I had to install ruby but turns out my mac already has one, so I was like that's great (but it's NOT). Then there was something to do with "gems" and "gemfiles". Then there was jekyll and themes. It was tough to be brutally honest.

But here I am now, my website is up and running and it's in decent shape for now. Here is my breakdown to how you should go about building your own website on github pages:

## Install Ruby and Bundler

If you're using a mac, you already have ruby, but you want it install the latest version. Since you cannot have conflicting versions on the same machine (you can but it creates complications), the recommendation is to use `rbenv` which helps in managing different ruby environments on your system. Use this  [resource](https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-macos "Install Ruby") to get a better sense. This link also has the way to install bundler which you'd use to essentially build your website from your local system.

## Set up a Github repository

Create a new repository specifically with the name: {your-github-username.github.io}. Now, it is important you get this right, otherwise your website ain't going live. Your github username should be typed "as is", absolutely no modifications. So if your github username is 'random123', your website needs to be 'random123.github.io'. Once created, clone it to your local system and that will become your project directory. This is where all your content goes that'll get uploaded to your website (that also includes the style and theme).

## Using Jekyll to create a website

The absolute best way to create a customized website is to use [jekyll](https://jekyllrb.com "Jekyll"). It's basically a Ruby gem, so you already got it through the first step here. After cloning the github repo, `"cd your-repo"` from the Terminal or command line and then type `"bundle exec jekyll new ."` or  `jekyll new .` (whichever works for you). Note that the period (.) just means that you aren't creating a subdirectory inside your repo and just creating a bunch of files in the repo itself. Once you run this command, you'll see a bunch of files created in your repo. Open the file named "Gemfile" and do the following:
1. You might find this (or something similar):
    ```yaml
    source "https://rubygems.org"
    # Hello! This is where you manage which Jekyll version is used to run.
    # When you want to use a different version, change it below, save the
    # file and run `bundle install`. Run Jekyll with `bundle exec`, like so:
    #
    #     bundle exec jekyll serve
    #
    # This will help ensure the proper Jekyll version is running.
    # Happy Jekylling!
    gem "jekyll", "~> 4.0.0"
    # This is the default theme for new Jekyll sites. You may change this to anything you like.
    gem "minima", "~> 2.5"
    # If you want to use GitHub Pages, remove the "gem "jekyll"" above and
    # uncomment the line below. To upgrade, run `bundle update github-pages`.
    # gem "github-pages", group: :jekyll_plugins
    # If you have any plugins, put them here!
    group :jekyll_plugins do
      gem "jekyll-feed", "~> 0.12"
    end

    # Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
    # and associated library.
    install_if -> { RUBY_PLATFORM =~ %r!mingw|mswin|java! } do
      gem "tzinfo", "~> 1.2"
      gem "tzinfo-data"
    end

    # Performance-booster for watching directories on Windows
    gem "wdm", "~> 0.1.1", :install_if => Gem.win_platform?
    ```

2. As mentioned in this already, if you want to use Github Pages, uncomment (or remove the #) before the line "# gem "github-pages", group: :jekyll_plugins" and comment (or add a #) in front of the line "gem "jekyll", "~> 4.0.0". So it should look something like:

    ```yaml
    ...
    ...
    ...
    # Happy Jekylling!
    # gem "jekyll", "~> 4.0.0"
    ...
    ...
    gem "github-pages", group: :jekyll_plugins
    ...
    ...
    ```

    Note that for windows, there are a bunch of other things that you might need to take care, most of my knowledge about all this is for macOS, so make sure you don't miss out those extra things.

3. Save and close the Gemfile
4. Open the _config.yml file and edit the file with your basic information 
5. On your terminal, run `bundle update` (this needs to be done every time you modify your config.yml file) and then run  `bundle exec jekyll build`
5. Push all the new files to your repo

Technically your website is ready and published. To check that, you should be able to see an 'environment' option on your repo or you could run `bundle exec jekyll serve` to check locally what it looks like. Another way is to just type in the name of your github.io website in a browser.

## Customizing your website

Now, if you aren't someone who has experience in 'html' or 'css' (if you've made it this far, I am assuming you aren't), it's pretty darn hard to customize it yourself or even try to figure it out by yourself. The best way is to use a theme that someone's already developed. You can find a lot of examples on github where people have developed their own themes that you can use. [Here](https://github.com/Sylhare/Type-on-Strap) is one such example. Just follow instructions on these repositories and you should be good.

Once you have that set up, you can just keep adding posts in your `_posts` directory and you've built your website/blog to showcase your work (importantly without too much of a hassle and free of cost).

## Experiment

If you're like me, you're going to want to customize it further to make it completely personal. I suggest keep experimenting with it and hope you come out with an awesome website.

_All the best and thanks for reading!_

## Additional references:

1. [Github Pages](https://help.github.com/en/github/working-with-github-pages/getting-started-with-github-pages)

2. [Jekyll documentation](https://jekyllrb.com/docs/step-by-step/01-setup/)
