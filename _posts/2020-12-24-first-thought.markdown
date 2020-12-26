---
layout: post
title:  "Blogging, Jekyll, GitHub pages"
excerpt: "Setting up this blog took way longer than expected. I describe how I set up mine using Jekyll and GitHub Pages. "
comments: true
date:   2020-12-24
---

**Outcome**. Have your main website hosted at `<username>.github.io` in one GitHub directory. Have your blog hosted at `<username>.github.io/blog` in another GitHub directory. 

**Prelude**. Hello world! I’m a first year PhD student at Stanford. I decided to make a blog documenting my thoughts throughout my graduate studies. 

I’ve been meaning to set this blog up for a while now. The honest reason why I didn’t set it up earlier is because figuring out how to have two repositories (one for my main website and another for my blog) hosted at `rosewang2008.github.io` and `rosewang2008.github.io/blog` took way longer than expected -- an embarrassing two hours! That is why my first blog post is on how I set up my website and blog. 

For people interested in the source code for my website and blog, take a look at [this repo](https://github.com/rosewang2008/rosewang2008.github.io) and [this repo](https://github.com/rosewang2008/blog). 

**Website setup.** 
I really like [Jon Barron’s website design](https://jonbarron.info/). Luckily, he has his website open-sourced, making it really easy for others to set up a similar site. I forked his site, and made my own modifications. The code for my site can be found [here](https://github.com/rosewang2008/rosewang2008.github.io). 

1. Make a public repository that’s titled `<username>.github.io`, where `<username>` is your GitHub username. My website github repository is named [rosewang2008.github.io](https://github.com/rosewang2008/rosewang2008.github.io) because `rosewang2008` is my GitHub username. 

<p style="text-align:center">
    <img src="/blog/assets/blog_setup/repo_name.png" width="600" align="middle">
</p>

2. Put your website code in this repository, master branch.

<p style="text-align:center">
    <img src="/blog/assets/blog_setup/code.png" width="600" align="middle">
</p>

3. Now, onto hosting your site at `<username>.github.io`. Click on “Settings” on the top, right button. 

<p style="text-align:center">
    <img src="/blog/assets/blog_setup/settings.png" width="600" align="middle">
</p>

4. On the Settings page, scroll down to Section “GitHub Pages”. Under “Source”, click on the master branch. This indicates which branch GitHub Pages should build your site from. Your site should now be published at `<username>.github.io`! 

<p style="text-align:center">
    <img src="/blog/assets/blog_setup/host.png" width="600" align="middle">
</p>


**Blog setup.** I really like [Andrej Karpathy’s blog](http://karpathy.github.io/) which uses both Jekyll and GitHub pages. However, unlike Andrej who hosts his blog directly under `<username>.github.io`, I wanted to host mine under `<username>.github.io/blog`.

1. [Install Jekyll for your operating system](https://jekyllrb.com/docs/installation/)

2. Create a new GitHub repository called `blog`, clone it on your laptop, and go into the new cloned directory with `cd blog`. 

3. Run `jekyll new . --force`. This initializes the Jekyll template code for creating your site. 

4. There are two important files that are created from above and that you need to edit in order for your blog to be hosted with GitHub pages. The first file is: `_config.yml`. Edit `baseurl` to `baseurl: “/blog”` (your repository name), and `url` to `url: https://<username>.github.io`. 

<p style="text-align:center">
    <img src="/blog/assets/blog_setup/config.png" width="600" align="middle">
</p>

5. The second file is `Gemfile`. The file already gives instructions for what lines to edit, but for clarity, the end result should look like the picture below, i.e. the line with the first red arrow should be commented out, and the line with the second red arrow should NOT be commented out. 

<p style="text-align:center">
    <img src="/blog/assets/blog_setup/gemfile_pic.png" width="600" align="middle">
</p>

6. Add, commit and push your changes. Like in the website, all of your code should live on the master branch.

7. Now, onto deploying your code to `<username>.github.io/blog`. This will be similar to steps 3 and 4 from **Website Setup**. Go to the `blog` repository “Settings”, scroll to the section on GitHub Pages, and then select your source to be your master branch.

<p style="text-align:center">
    <img src="/blog/assets/blog_setup/host_blog.png" width="600" align="middle">
</p>

8. You can now visit your site at `<username>.github.io/blog`! FYI it may take a few minutes for your site to properly build. 


**Notes.** I’ve read several blog-setup tutorials that suggest having your content in a separate branch called `gh-pages`. I found this to be unnecessary. I have my blog built directly from the main master branch. 

