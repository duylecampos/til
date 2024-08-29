---
layout: post
title:  "How to count equal elements in a hash"
date:   2024-07-27 14:39:00 -0300
categories: ruby
links: https://ruby-doc.org/3.2.2/Enumerable.html#method-i-tally
---


```ruby
# Giving the following list of locations
locations = [
  { "city": "New York", "state": "NY" },
  { "city": "Los Angeles", "state": "CA" },
  { "city": "San Francisco", "state": "CA" },
  { "city": "Chicago", "state": "IL" },
  { "city": "Springfield", "state": "IL" },
  { "city": "Houston", "state": "TX" },
  { "city": "Dallas", "state": "TX" },
  { "city": "Miami", "state": "FL" },
  { "city": "Tampa", "state": "FL" },
  { "city": "Denver", "state": "CO" },
  { "city": "Colorado Springs", "state": "CO" },
  { "city": "Seattle", "state": "WA" },
  { "city": "Spokane", "state": "WA" },
  { "city": "Boston", "state": "MA" },
  { "city": "Worcester", "state": "MA" },
  { "city": "Atlanta", "state": "GA" },
  { "city": "Savannah", "state": "GA" },
  { "city": "Austin", "state": "TX" },
  { "city": "San Antonio", "state": "TX" },
  { "city": "Orlando", "state": "FL" },
  { "city": "Jacksonville", "state": "FL" },
  { "city": "Portland", "state": "OR" },
  { "city": "Eugene", "state": "OR" },
  { "city": "Detroit", "state": "MI" },
  { "city": "Grand Rapids", "state": "MI" },
  { "city": "Phoenix", "state": "AZ" },
  { "city": "Tucson", "state": "AZ" },
  { "city": "Las Vegas", "state": "NV" },
  { "city": "Reno", "state": "NV" },
  { "city": "Charlotte", "state": "NC" },
  { "city": "Raleigh", "state": "NC" },
  { "city": "Minneapolis", "state": "MN" },
  { "city": "St. Paul", "state": "MN" },
  { "city": "Kansas City", "state": "MO" },
  { "city": "St. Louis", "state": "MO" },
  { "city": "Salt Lake City", "state": "UT" },
  { "city": "Provo", "state": "UT" },
  { "city": "Nashville", "state": "TN" },
  { "city": "Memphis", "state": "TN" }
]

# You can get the number of cities in each state by doing
locations.map{ |location| location[:state] }.tally
# > {"NY"=>1, "CA"=>2, "IL"=>2, "TX"=>4, "FL"=>4, "CO"=>2, "WA"=>2, "MA"=>2, "GA"=>2, "OR"=>2, "MI"=>2, "AZ"=>2, "NV"=>2, "NC"=>2, "MN"=>2, "MO"=>2, "UT"=>2, "TN"=>2}
```