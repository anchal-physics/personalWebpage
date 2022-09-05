---
layout: post
title:  "Loving GitHub Actions!"
date:   2022-09-05 12:16:50 -0700
author: Anchal Gupta
categories: opinion
---
This is gonna be a short review from a fairly new user of CI/CD with limited
experience. I used to use Travis CI for some personal repo python code running
as well as some work-related latex compilation and deployment of generated pdf.
In both cases, setting up Travis to work was not always easy or straight
forward (at least to noobs like me). One of the reasons I felt it consumed time
was because I had to search for codes in other repos or StackExchange, and
often the code needed to be copied manually and adopted. And then, Travis
stopped me from using CI for free for public repos. It turned out the free
usage was for limited minutes.

I wanted to have a better solution. Most of my work-related repos are hosted on
a GitLab enterprise, and our collaboration runs GitLab runner
servers for all to use. So using the in-built GitLab ci runner has been always
convenient with easy access to docker containers. But I couldn't use the same
benefits for my personal projects because I couldn't access such servers. So
one better solution to my problem was to use an old laptop at home, make it
Debian, and set it up as a server that my repos can use for GitLab runners.
The hard disk of this computer was dying though and replacing that became a task I
could procrastinate for some time.

And then, I came across an article about GitHub Actions. I can't remember from
where. I got immediately sucked into it. It provides free runners for
public repos, and setting up GitHub actions is even easier than GitLab ci. The
configuration structure based on yaml is concise, helpful, and simply
beautiful. Beautiful also because the format is very similar to how I have been
imagining my ideal laser interferometer operation script in yaml.

The fact, that you can call in favors from the online community, by using their
defined actions in our configuration line with a simple step statement is
amazing. This ruled out all issues mentioned above while setting up
Travis. The GitHub Actions marketplace is amazing and fills me with joy and hope
about future collaboration in open public development. I just made this webpage
and for deploying it to gh-pages, I simply use:

{% highlight yaml %}
jobs:
  BuildAndDeploy:
    .
    .
    steps:
      .
      .
      - name: Deploy webpage
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./_site/
{% endhighlight %}

Thanks to [peaceiris/actions-gh-pages@v3](https://github.com/peaceiris/actions-gh-pages).

So I'm very happy about GitHub Actions. I wish I had come to know about it
earlier. That was my first post, thanks for reading.
