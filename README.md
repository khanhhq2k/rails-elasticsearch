# README

after adding
  include Elasticsearch::Model
  include Elasticsearch::Model::Callbacks
 to article model

$ rails console

# Create the index for Service model on elasticsearch
> Article.__elasticsearch__.create_index!
=> {"acknowledged"=>true}

# Import current Service records into the index
> Article.import

# Sample search returning total results
> Article.__elasticsearch__.search("mykeyword").results.total
=> 2
