+++
title = "Introducing Icarus and its features"
date = "2015-10-10T16:56:43+02:00"
tags = ["theme", "hugo", "static sites"]
categories = ["theme"]
menu = ""
images = []
banner = "banners/placeholder.png"
+++

Icarus is a responsive and customizable theme for bloggers. It's a port of the same-named theme for [Hexo](//hexo.io) made by [Ruipeng Zhang](https://github.com/ppoffice). Noteworthy features of this Hugo theme are the integration of a comment-system powered by Disqus, localization (l10n) support, syntax highlighting for source code, optional widgets for the sidebar and a handful [shortcodes](http://gohugo.io/extras/shortcodes/) to make your life easier.


## Get the theme

I assume you've Git installed. Inside the folder of your Hugo site run

    $ mkdir themes
    $ cd themes
    $ git clone git@github.com:digitalcraftsman/hugo-icarus-theme.git

You should see a folder called `hugo-icarus-theme` inside the `themes` directory that we created a few moments ago. For more information read the official [setup guide](https://gohugo.io/overview/installing/) of Hugo.


## Setup

In the next step navigate to the `exampleSite` folder at `themes/hugo-icarus-theme/exampleSite/`. Its structure should look similar to this:

    exampleSite
    ├── config.toml
    ├── content
    │   └── post
    │       ├── creating-a-new-theme.md
    │       ├── go-is-for-lovers.md
    │       ├── hugo-is-for-lovers.md
    │       ├── introducing-icarus-and-its-features.md
    │       ├── linked-post.md
    │       └── migrate-from-jekyll.md
    ├── data
    │   └── l10n.toml
    └── static
        └── banners
            └── placeholder.png

In order to get your site running, you need to copy `config.toml` and `data/l10n.toml` into the root folders.


## The config file

Now, let us take a look into the `config.toml`. Feel free to play around with the settings.


### Comments

The opional comment system is powered by Disqus. Enter your shortname to enable the comment section under your posts.

    disqusShortname = ""


### Menu

You can also define the items menu entries as you like. First, let us link a post that you've written. We can do this in the frontmatter of the post's content file by setting `menu` to `main`. Take a look at the menu if you want to see a live example.

    +++
    menu = "main"
    +++

Furthermore, we can add entries that don't link to posts. Back in the `config.toml` you'll find a section for the menus:

    [[params.menu]]
        before = true
        label  = "Home"
        link   = "/"

Define a label and enter the URL to resource you want to link. With `before` you can decide whether the link should appear before **or** after all linked posts in the menu. `Home` appears before the linked post, `Tags` and `Categories` after them (as in the menu above).


### Tell me who you are

Maybe you noticed the profile section on the left. Add your social network accounts to the profile section on the left by entering your username under `social`. The links to your account will be create automatically.


### Widgets

On the right, you can see some useful widgets that you can activate as you like. You can deactivate them under `params.widgets`:

    [params.widgets]
        recent_articles = false
        categories = true
        tags = true
        tag_cloud = true


## Localization (l10n)

You don't blog in English and you want to translate the theme into your native locale? No problem. Take a look in the `data` folder and you'll find a file `l10n.toml` that we've copied at the beginning. It contains all strings related to the theme. Just replace the original strings with your own.


## Linking thumbnails

After creating a new post you can define a banner by entering the relative path to the image.

    banner = "banners/placeholder.png"

This way you can store them either next to the content file or in the `static` folder.


## Mathematical equations

In case you need to display equations you can insert your LaTeX or MathML code and it works out of the box thanks to [MathJax](https://www.mathjax.org).

    \[ z = r \cdot (\sin{\phi} + \cos{\phi} \cdot i) \]

\[ z = r \cdot (\sin{\phi} + \cos{\phi} \cdot i) \]


## Shortcodes

Last but not least I included some useful [shortcodes](http://gohugo.io/extras/shortcodes/) to make your life easier.

### Gallery

This way you can include a gallery into your post. Copy the code below into your content file and enter the relative paths to your images.

    {{</* gallery
        "/banners/placeholder.png"
        "/banners/placeholder.png"
        "/banners/placeholder.png"
    */>}}

<p></p>

{{< gallery "/banners/placeholder.png" "/banners/placeholder.png" "/banners/placeholder.png" >}}


### JSFiddle

It works the same with JSFiddle examples you want to showcase. The parameter `id` consists of the username and id of the example.

    {{</* jsfiddle id="zalun/NmudS" */>}}

<p></p>

{{< jsfiddle id="zalun/NmudS" >}}

As descibed in the [docs of JSFiddle](http://doc.jsfiddle.net/use/embedding.html), you can define which tabs will be shown. Enter the tabs you want to see separated by a comma in the `tabs` parameter.

    {{</* jsfiddle id="zalun/NmudS" tabs="html,result" */>}}

Do you see the difference?

{{< jsfiddle id="zalun/NmudS" tabs="html,result" >}}


## Nearly finished

In order to see your site in action, run Hugo's built-in local server.

    $ hugo server

Now enter [`localhost:1313`](http://localhost:1313) in the address bar of your browser.


## Contributing

Have you found a bug or got an idea for a new feature? Feel free to use the [issue tracker](//github.com/digitalcraftsman/hugo-icarus-theme/issues) to let me know. Or make directly a [pull request](//github.com/digitalcraftsman/hugo-icarus-theme/pulls).


## License

This theme is released under the MIT license. For more information read the [License](https://github.com/digitalcraftsman/hugo-icarus-theme/blob/master/LICENSE.md).


## Annotations

Thanks to [Steve Francia](//github.com/spf13) for creating Hugo and the awesome community around the project.
