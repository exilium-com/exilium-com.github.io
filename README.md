[![github pages](https://github.com/exilium-com/exilium-com.github.io/actions/workflows/main.yml/badge.svg)](https://github.com/exilium-com/exilium-com.github.io/actions/workflows/main.yml)
# Notes

Now using [Hugo](https://gohugo.io) to build web site.
Hugo binaries are installed trivially with
`brew install hugo`, build with `hugo -D` into the public folder, and
run locally with `hugo serve`.

The [theme](https://github.com/themefisher/meghna-hugo) includes a LOT of features
we are not currently using, look at all the disabled sections for ideas.
The theme [documentation](https://docs.gethugothemes.com/meghna/) may help.

This [Hugo intro](https://www.ii.com/themeless-gitless-intro-hugo/#_edit_the_archetype_for_new_md_content_files) has enough depth to actually understand what is going on.

## Add a new Author

`hugo new --kind author content/english/author/firstname-lastname.md`, then edit content/english/author/firstname-lastname.md.
Add a picture to static/images/team/firstname-lastname.jpg, reference it in the md file.

Note that team members highlighted in home page are duplicative of this, those are managed in data/en/team.yml
for English, and similarly for other languages.
## Add a new post

`hugo new --kind post content/english/blog/title-of-my-post.md`, then edit content/english/blog/title-of-my-post.md. Reference
author name from previously created author.
If you need math in the post, uncomment the `hasMath` line.

## Add a new project

`hugo new --kind project content/english/project/my-project-name.md`, then edit content/english/project/my-project-name.md.
If you need math in the post, uncomment the `hasMath` line.

Add a picture for the project in static/images/portfolio/my-project-image.jpg and reference in the md file.

Note that projects highlighted in the home page are duplicative of this, those are managed in data/en/portfolio.yml
for English and similarly for other languages.

# Credits

Many photos on this site originated from <a href="https://unsplash.com/collections/65666478/keys%2C-locks%2C-and-chains?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>, thanks to various contributors:
- Photo by <a href="https://unsplash.com/@jdent?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Jason Dent</a>

test