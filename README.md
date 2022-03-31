# My Blog

This blog is built with Hugo using the minimal theme 'PaperMod'.
<br>
You can browse the Hugo website for various starter themes for blogs, documentation, portfolios etc by clicking this link 👉
[Hugo Themes](https://themes.gohugo.io/)

## Hugo PaperMod
My reasons for choosing Hugo & PaperMod:
<ul>
<li> I chose Hugo because it's super fast ⚡️ &has great documentation 📝 
</li>
<li> I chose PaperMod because I loved the minimal design 🎨 and it also uses vanilla JS & CSS 🍦</li>
<li> I didnt want lots of frameworks/ packages/ plugins because it feels a bit overkill for a small personal blog that is intended to document my tech learning/ journey 👩🏼‍💻
<li> Chose to use Markdown instead of a Headless CMS to hopefully create a good habit of using Git/GitHub more frequently 😅
</ul>

## Getting Started
I used these references to help with installation and setting up on my local and remote: 
* [PaperMod- Installation Guide](https://github.com/adityatelange/hugo-PaperMod/wiki/Installation)

* [Hugo- Add a Theme](https://gohugo.io/getting-started/quick-start/#step-3-add-a-theme)

* [GitHub - Importing Projects](
https://docs.github.com/en/get-started/importing-your-projects-to-github/importing-source-code-to-github/adding-locally-hosted-code-to-github)

### Terminal Commands 🖥
In my terminal I entered the following commands to create a new folder & hugo site:
```
ls
cd desktop
hugo new site myblog -f yml
cd myblog
```
Initialised git and added theme submodule and added theme to config.yml:
```
git init
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
git submodule update --init --recursive
echo theme: \PaperMod >> config.yml
```
* Might need for future reference to update theme:
git submodule update --remote --merge

Ran the Hugo Server to check it all works nicely:
```
hugo server -D
```
Created my repository on GitHub and copied & pasted the GitHub CLI link followed by staging, committing, pushing files to repository:

```
git add . && git commit -m "first commit"
git remote add origin git@github.com:ewainy/myblog.git
git push -u origin main
```
Created README.md
```
touch README.md
echo "# My Blog">README.md 	
git add README.md 
git commit -m "README.md added" 
git push
```

### Config.yml 
Added example config to config.yml file mentioned in PaperMod installation Wiki on a new branch (will customise it later):
``` 
git checkout -b exampleConfig
```
```yml
baseURL: "https://examplesite.com/"
title: ExampleSite
paginate: 5
theme: PaperMod

enableRobotsTXT: true
buildDrafts: false
buildFuture: false
buildExpired: false
pygmentsUseClasses: true

googleAnalytics: UA-123-45

minify:
    disableXML: true
    minifyOutput: true

params:
    env: production # to enable google analytics, opengraph, twitter-cards and schema.
    title: ExampleSite
    description: "ExampleSite description"
    keywords: [Blog, Portfolio, PaperMod]
    author: Me
    # author: ["Me", "You"] # multiple authors
    images: ["<link or path of image for opengraph, twitter-cards>"]
    DateFormat: "January 2, 2006"
    defaultTheme: auto # dark, light
    disableThemeToggle: false

    ShowReadingTime: true
    ShowShareButtons: true
    ShowPostNavLinks: true
    ShowBreadCrumbs: true
    ShowCodeCopyButtons: false
    disableSpecial1stPost: false
    disableScrollToTop: false
    comments: false
    hidemeta: false
    hideSummary: false
    showtoc: false
    tocopen: false

    assets:
        # disableHLJS: true # to disable highlight.js
        # disableFingerprinting: true
        favicon: "<link / abs url>"
        favicon16x16: "<link / abs url>"
        favicon32x32: "<link / abs url>"
        apple_touch_icon: "<link / abs url>"
        safari_pinned_tab: "<link / abs url>"

    label:
        text: "Home"
        icon: /apple-touch-icon.png
        iconHeight: 35

    # profile-mode
    profileMode:
        enabled: false # needs to be explicitly set
        title: ExampleSite
        subtitle: "This is subtitle"
        imageUrl: "<img location>"
        imageWidth: 120
        imageHeight: 120
        imageTitle: my image
        buttons:
            - name: Posts
              url: posts
            - name: Tags
              url: tags

    # home-info mode
    homeInfoParams:
        Title: "Hi there \U0001F44B"
        Content: Welcome to my blog

    socialIcons:
        - name: twitter
          url: "https://twitter.com/"
        - name: stackoverflow
          url: "https://stackoverflow.com"
        - name: github
          url: "https://github.com/"

    analytics:
        google:
            SiteVerificationTag: "XYZabc"
        bing:
            SiteVerificationTag: "XYZabc"
        yandex:
            SiteVerificationTag: "XYZabc"

    cover:
        hidden: true # hide everywhere but not in structured data
        hiddenInList: true # hide on list pages and home
        hiddenInSingle: true # hide on single page

    editPost:
        URL: "https://github.com/<path_to_repo>/content"
        Text: "Suggest Changes" # edit text
        appendFilePath: true # to append file path to Edit link

    # for search
    # https://fusejs.io/api/options.html
    fuseOpts:
        isCaseSensitive: false
        shouldSort: true
        location: 0
        distance: 1000
        threshold: 0.4
        minMatchCharLength: 0
        keys: ["title", "permalink", "summary", "content"]
menu:
    main:
        - identifier: categories
          name: categories
          url: /categories/
          weight: 10
        - identifier: tags
          name: tags
          url: /tags/
          weight: 20
        - identifier: example
          name: example.org
          url: https://example.org
          weight: 30
          
# Read: https://github.com/adityatelange/hugo-PaperMod/wiki/FAQs#using-hugos-syntax-highlighter-chroma
# pygmentsUseClasses: true
# markup:
#     highlight:
#         # anchorLineNos: true
#         codeFences: true
#         guessSyntax: true
#         lineNos: true
#         style: monokai
```
Staged & committed file & pushed the branch, which creates a Pull Request:
```
git add config.yml
git commit -m "example config + language code"
git push --set-upstream origin exampleConfig
```
I then reviewed and merged PR into main on GitHub and deleted the branch.

\*Note to self, Remember to delete branch on local 🙃\*
```
git checkout main
git branch -d exampleConfig
git fetch origin main
git merge
```
Panic Over! 😅

### Create post.md archetype
**What are archetypes?**
> Archetypes are templates used when creating new content 

They contain preconfigured **front matter** so it is easy to generate new posts on the fly!

**What is front matter?**
> Front Matter is structured metadata that lives at the top of your content files that allows you to add custom variables to your pages.

Examples of front matter you might have for a blog: 'Title' 'Summary' 'Date' 'Author' 

**Read more about archetypes in Hugo** 👉 [Hugo Archetypes](https://gohugo.io/content-management/archetypes/#create-a-new-archetype-template)


Create file called 'post.md' in archetypes folder archetypes/post.md
<br>
Copied & pasted example from PaperMod

```yml
---
title: "My 1st post"
date: 2020-09-15T11:30:03+00:00
# weight: 1
# aliases: ["/first"]
tags: ["first"]
author: "Me"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Desc Text."
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/<path_to_repo>/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---
```
---
We will then use `hugo new` followed by `post/my-first-post.md`. Hugo uses the content section to find the most suitable archetype template in a project. Since we dont currently have any directories in the content path it will create that for us too.
It will then create the new file `my-first-post.md` which will have this pathway: `content/post/my-first-post.md`
<br>
Hugo will look for the archetype that **matches** `post` or will fall back on a `default` archetype. Since we have created a `post` archetype it will use the front matter we created in this archetype file to generate the front matter for us in our newly created `my-first-post` file. 

```
hugo new post/my-first-post.md
```

**Further explanation:**
> By default, everything created within a section will use the content type that matches the root section name. For example, Hugo will assume that posts/post-1.md has a posts content type. If you are using an archetype for your posts section, Hugo will generate front matter according to what it finds in archetypes/posts.md. [Hugo Content Section](https://gohugo.io/content-management/sections/)

<br>
I think that's about it for setting up and getting started! 🤔 

I will be adding my `customisations` in a seperate file on this GitHub repository which will be called [`Customising.md`](./Customising.md)
