# README
guide reference:
https://www.sitepoint.com/full-text-search-rails-elasticsearch/

after adding
  include Elasticsearch::Model
  include Elasticsearch::Model::Callbacks
 to article model

$ rails console

# Create the index for Article model on elasticsearch
> Article.__elasticsearch__.create_index!
=> {"acknowledged"=>true}

# Import current Article records into the index
> Article.import

# Sample search returning total results
> Article.__elasticsearch__.search("mykeyword").results.total
=> 2
