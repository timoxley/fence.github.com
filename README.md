# A word about Markdown

Markdown is a practical language, built for site owners. Like open
source scripting languages it was implemented before it was designed.
Unlike some open source scripting languages, however, it has not
seen many official changes since its release. This means that the
official spec hasn't gained things that are needed for people besides
site owners to use it, like HTML sanitization. Many Markdown projects
have filled in the gaps, though, most notably [PHP-Markdown],
[Stack Overflow], and [GitHub].

  [PHP-Markdown]: http://michelf.com/projects/php-markdown/
  [Stack Overflow]: http://stackoverflow.com/
  [GitHub]: http://github.com/

GitHub made some additions to their Markdown library for programmers
and for users of their site. These include [emoji], [issue linking],
and [syntax highlighting].

  [emoji]: https://github.com/blog/816-emoji
  [issue linking]: http://github.github.com/github-flavored-markdown/
  [syntax highlighting]: https://github.com/blog/832-rolling-out-the-redcarpet
  
These changes were not well received by everyone. Some were
disappointed that they invented syntax rather than [use what
PHP-Markdown had](http://michelf.com/projects/php-markdown/extra/#fenced-code-blocks).
Others thought they should call it something other than Markdown. In
general these changes delighted users of GitHub, though.

Slowly but surely an inter-language Markdown community that sanitizes 
HTML by default, [allows strikethrough], and supports neat features like
codeblocks is emerging.

  [allows strikethrough]: https://github.com/tanoku/redcarpet/blob/master/lib/redcarpet.rb#L87
  
If you're a Markdownista who believes in progress, times are good.

# Code Blocks in READMEs on GitHub

GitHub decided to take the explicit route on syntax highlighting. This
is a different choice than what Stack Overflow took. It takes away the
burden of detecting the language from Markdown processors.

This is a good, but not optimal, decision. Since a syntax highlighter 
is already a sophisticated piece of software, having Markdown 
processors detect the language isn't a major pain point. What would be 
a problem is a README author having code presented with the wrong 
highlighter and no way to fix this. This would arguably be worse than 
not highlighting syntax at all. It would be better for GitHub to
detect the language automatically, but only when no language is
specified.

The result is that in order for code to be syntax highlighted, it must
be fenced. The standard code block in Markdown starts with four
spaces. Here is an example JavaScript factorial function indented with
four spaces, as per the markdown spec:

    function factorial(n) {
      return n < 2 ? 1 : n * factorial(n - 1);
    }

See? It isn't highlighted. Now here's one fenced with
triple-backquotes:

```
    function factorial(n) {
      return n < 2 ? 1 : n * factorial(n - 1);
    }
```

Much better, if you're in the majority.

# Please Fence!

If you like syntax highlighting and you don't object to Markdown being
extended to be more useful, please fence.

If you respecfully disagree with GitHub's decision to extend Markdown
and wish they'd call it something else, please pretend it's something
else and fence.

If you're using Markdown for your README because it's popular on
GitHub, please fence.

If your README is most often read on GitHub, please fence.

I have a much easier time scanning a README if syntax highlighting is
enabled.

# Expanding this movement

This is a rough draft, so if you have suggestions, please make them.
Please make a pull request; if I like it I'll merge it in.

Please, when you wish a README was in Markdown, if you have spare time
consider letting the author know, and possibly sending a pull request.
Provide a link to this document or a similar resource if you're not
sure the author knows about this. If you're hesitant to link them to
this page because of its content, please create an issue and let me
know why.

One reason not to fence code blocks is laziness. A bot that sends pull
requests could help with this. It is for this reason I created an
organization, though I haven't yet allocated time to do it. If you'd
like to help, please let me know!

# Improving the situation in the future

There are a lot of great text formats besides Markdown but I prefer
Markdown and so do many others. It is my hope that Markdown continues
to evolve, and I think it will. One thing I haven't yet seen that
Markdown needs is a commonly-used lint tool.
[I'm not the first person to think so.](https://twitter.com/#!/gruber/status/76555999460327424)

Another thing that's needed is for more tools to support
GitHub-flavored markdown. Specifically it seems that Java is lacking
in this area.

Authors
-------

* Ben Atkin <<ben@benatkin.com>>

<a rel="license" href="http://creativecommons.org/publicdomain/zero/1.0/">
  <img src="http://i.creativecommons.org/p/zero/1.0/88x31.png" style="border-style: none;" alt="CC0" />
</a>

To the extent possible under law, the authors have waived all copyright and related or neighboring rights to this work.
