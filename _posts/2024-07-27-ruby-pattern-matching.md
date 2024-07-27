---
layout: post
title:  "Ruby Pattern Matching"
date:   2024-07-27 14:39:00 -0300
categories: ruby
links: https://www.toptal.com/ruby/ruby-pattern-matching-tutorial
---

We can use Pattern Matching to check for complex structure on case statements.
Let's imagine a scenario where we got a list of entities following the example of [GraphQL union types](https://graphql.org/learn/schema/#union-types).

```ruby
results = [
    {"__typename": "Human","name": "Han Solo","height": 1.8},
    {"__typename": "Human","name": "Leia Organa","height": 1.5},
    {"__typename": "Starship","name": "TIE Advanced x1","length": 9.2}
]

results.each do |r|
    case r
    in {name:, height:}
        puts "#{name} is #{height} tall"
    in {name:, length:}
        puts "#{name} is #{length} long"
    else
        puts "Sorry, we aren't able to describe this data"
    end
end
# OUTPUT:
# Han Solo is 1.8 tall
# Leia Organa is 1.5 tall
# TIE Advanced x1 is 9.2 long
```