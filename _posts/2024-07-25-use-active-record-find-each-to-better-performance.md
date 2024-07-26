---
layout: post
title:  "You should use find_each to reduce memory usage"
date:   2024-07-25 09:00:07 -0300
categories: rails
links: https://medium.com/lynns-dev-blog/rails-find-each-v-s-find-in-batches-v-s-in-batches-d5ca9bfe37d
---

```ruby
# instead of 
User.where(active: true).all.each do |user| 
    # do anything with user object
end
# you should do
User.where(active: true).find_each do |user|
    # do anything with user object
end
```

The `.all.each` option will load all the users in the memory and then iterate over the list, which can cause issues with memory usage. While the `.find_each` will fetch the data from the db in batches, that way reducing the amount of memory required/used.

If needed, you can configure the batch size (default value is 1000) by doing the following:
```ruby
User.where(active: true).find_each(batch_size: 100) do |user|
    # ...
end
```