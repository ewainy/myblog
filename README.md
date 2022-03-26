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

### Mac Terminal Commands 🖥
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