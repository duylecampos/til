---
layout: post
title:  "You can use numbered parameters in ruby blocks"
date:   2024-07-24 18:19:07 -0300
categories: ruby
---
Since Ruby 2.7, it's possible to access the parameters in a block using the numbered parameters feature.  This allows us to easily write simple blocks.
```ruby
# instead of
[{key: 'foo'}, {key: 'bar'}].find {|item| item[:key] == 'foo' }
# you can do
[{key: 'foo'}, {key: 'bar'}].find {_1[:key] == 'foo'}
```