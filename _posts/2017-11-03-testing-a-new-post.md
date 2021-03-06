---
layout: post
title: "Testing a New Post"
date: 2017-11-03
---

# Writing posts

One of Jekyll’s best aspects is that it is “blog aware”. What does this mean, exactly? Well, simply put, it means that blogging is baked into Jekyll’s functionality. If you write articles and publish them online, you can publish and maintain a blog simply by managing a folder of text-files on your computer. Compared to the hassle of configuring and maintaining databases and web-based CMS systems, this will be a welcome change!

## The Posts FolderPermalink

As explained on the [directory structure](https://jekyllrb.com/docs/structure/) page, the 

`_posts folder is where your blog posts will live. These files are generally [Markdown](https://daringfireball.net/projects/markdown/) or HTML, but can be other formats with the proper converter installed. All posts must have [YAML Front Matter](https://jekyllrb.com/docs/frontmatter/), and they will be converted from their source format into an HTML page that is part of your static site.`

### Creating Post FilesPermalink

To create a new post, all you need to do is create a file in the 

`_postsdirectory. How you name files in this folder is important. Jekyll requires blog post files to be named according to the following format:`

`YEAR-MONTH-DAY-title.MARKUP`
``
Where YEAR is a four-digit number, MONTH and DAY are both two-digit numbers, and MARKUP is the file extension representing the format used in the file. For example, the following are examples of valid post filenames:

`2011-12-31-new-years-eve-is-awesome.md`

`2012-09-12-how-to-write-a-blog.md`
``
## Including images and resourcesPermalink

Chances are, at some point, you’ll want to include images, downloads, or other digital assets along with your text content. While the syntax for linking to these resources differs between Markdown and Textile, the problem of working out where to store these files in your site is something everyone will face.

There are a number of ways to include digital assets in Jekyll. One common solution is to create a folder in the root of the project directory called something like 

`assets, into which any images, files or other resources are placed. Then, from within any post, they can be linked to using the site’s root as the path for the asset to include. Again, this will depend on the way your site’s (sub)domain and path are configured, but here are some examples in Markdown of how you could do this using the `

`absolute_urlfilter in a post.`

Including an image asset in a post:

`... which is shown in the screenshot below:`

`![My helpful screenshot]({{ "/assets/screenshot.jpg" | absolute_url }})`
``
Linking to a PDF for readers to download:

`... you can [get the PDF]({{ "/assets/mydoc.pdf" | absolute_url }}) directly.`
``
## A typical postPermalink

Jekyll can handle many different iterations of the idea you might associate with a “post,” however a standard blog style post, including a Title, Layout, Publishing Date, and Categories might look like this:

`---layout: posttitle:  "Welcome to Jekyll!"date:   2015-11-17 16:16:01 -0600categories: jekyll update---`
``
`You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `bundle exec jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.`
``
`To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.`
``
Everything in between the first and second 

`--- are part of the YAML Front Matter, and everything after the second `

`--- will be rendered with Markdown and show up as “Content”.`

## Displaying an index of postsPermalink

It’s all well and good to have posts in a folder, but a blog is no use unless you have a list of posts somewhere. Creating an index of posts on another page (or in a [template](https://jekyllrb.com/docs/templates/)) is easy, thanks to the [Liquid template language](https://docs.shopify.com/themes/liquid/basics) and its tags. Here’s a basic example of how to create a list of links to your blog posts:

`<ul>`

`  {% for post in site.posts %}`

`    <li>`

`      <a href="{{ post.url }}">{{ post.title }}</a>`

`    </li>`

`  {% endfor %}`

`</ul>`

Of course, you have full control over how (and where) you display your posts, and how you structure your site. You should read more about [how templates work](https://jekyllrb.com/docs/templates/) with Jekyll if you want to know more.

Note that the post variable only exists inside the for loop above. If you wish to access the currently-rendering page/posts’s variables (the variables of the post/page that has the 

`for loop in it), use the `

`pagevariable instead.`

## Displaying post categories or tagsPermalink

Hey, that’s pretty neat, but what about showing just some of your posts that are related to each other? For that you can use any of the [variables definable in Front Matter](https://jekyllrb.com/docs/frontmatter/). In the “typical post” section you can see how to define categories. Simply add the categories to your Front Matter as a [yaml list](https://en.wikipedia.org/wiki/YAML#Basic_components).

Now that your posts have a category or multiple categories, you can make a page or a template displaying just the posts in those categories you specify. Here’s a basic example of how to create a list of posts from a specific category.
