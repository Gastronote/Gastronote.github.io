---
layout: post
title: "How I build a website with Github/Jekyll"
date: 2025-04-18 22:07:00 +0800
categories: jekyll update
---

# Procedures
The procedure below is how I reach here as a *Windows 11* user. Let's assume we already have a Github account, and work in git-bash for the followings.
1. Install Ruby (in your local machine):
   `winget install RubyInstallerTeam.RubyWithDevKit.3.2` 
   You can change the version into any others Or follow the instructions \url{https://www.ruby-lang.org/en/documentation/installation/}{here}.

2. Update your Ruby gems:
   `gem update` 
   And don't forget to restart the terminal.

3. Install Jekyll and Bundler:
   `gem install jekyll bundler`
   Now, your local environment is ready.

4. Here I want to publish my page from a new branch `gh-pages`, then we can do 
   `git checkout --orphan gh-pages`

5. Navigate your directory to the repository:
   `mkdir docs` and then `cd docs`

6. Create a new Jekyll site:
   `jekyll new --skip-bundle .`
   Then Jekyll done all the work for me.

7. Find the Gemfile in \docs:
   1. comment out the line start with `gem "jekyll"` (add `#` in the front)
   2. activate the line `gem "github-pages"`(remove `#`)
   3. save and close
   
8. Run `bundle install` back in git-bash.
   
9. Find the `.gitignore` and add `Gemfile.lock` at the end.
    
10. Test your initial site locally:
    1.  Run `bundle exec jekyll serve`
    2.  You will find a server adress like: `http://127.0.0.1:4000/` in the results
    3.  Type it to your browser and take a look.
    
11. If everything is good:
    1.  `git add .`and `git commit -m 'Initial GitHub pages site with Jekyll'`
    2.  `git remote add origin https://github.com/USER/REPOSITORY.git` (modify your username and repository name)
    3.  `git push -u origin BRANCH` (push to the branch you're working on)
    
12. And you may see you site on `https://REPOSITORY`


### references
- https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- https://www.ruby-lang.org/en/documentation/installation/
- https://jekyllrb.com/docs/installation/windows/