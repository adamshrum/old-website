source "https://rubygems.org"

gem "sinatra"
gem "sass"
gem "erubis"
gem "rdiscount"
gem "rbs"

# we need our own pygments.rb because upstream's uses `#!/usr/bin/env python`
# and this will get py3k on arch linux. this commit changes it to python2
gem "pygments.rb",
  git: "git://github.com/haileysome/pygments.rb.git",
  ref: "12b7cfca829b694732ca6521e2314a36eb728329"
