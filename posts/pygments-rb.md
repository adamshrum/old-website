# pygments.rb

I wanted to call attention to one of the coolest Ruby libraries I've seen in a while — [pygments.rb](https://github.com/tmm1/pygments.rb). It's basically a Ruby wrapper for Python's excellent [Pygments](http://pygments.org/) library.

What makes pygments.rb so damn cool though is how it works. Unlike other Ruby Pygments wrappers, like GitHub's [Albino](https://github.com/github/albino), which work by shelling out to a Python process, pygments.rb actually embeds the Python interpreter in the Ruby process.

This means that pygments.rb doesn't have to restart Python and reload Pygments every time you want to highlight a bit of code. The Pygments code and Python VM is always ready to go. This helps out performance a fair bit too. According to Aman Gupta's (pygments.rb's author) benchmarks, it's about 11 times faster than Albino.

It isn't all sunshine and rainbows though. When I originally set up pygments.rb on [eval.in](http://eval.in), I had difficulty getting it to work properly unless I locked pygments.rb and the rubypython gem (which actually does the dirty work of embedding Python) to a specific version. If you have trouble getting pygments.rb to work, try adding this to your `Gemfile`:

    \ruby
    gem "rubypython",  "= 0.5.1"
    gem "pygments.rb", "= 0.1.3"

Once you've got it installed and working, using it is fairly straightforward:

    \ruby
    Pygments.highlight "puts 1 + 2", lexer: "ruby"

Ruby has its own syntax highlighting libraries, but none have the same kind of wide language support Pygments does. While it would be lovely if there was a Ruby library up to par with Pygments, for now pygments.rb seems to be the pragmatic choice.

Go check it out: [https://github.com/tmm1/pygments.rb](https://github.com/tmm1/pygments.rb)
