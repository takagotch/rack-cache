### rack-cache
---
https://github.com/rtomayko/rack-cache


```
gem install rack-cache

rake midleware

```

```ruby
require 'rack/cache'
use Rack::Cache,
  metastore: 'file:/var/cache/rack/meta',
  entitystore: 'file:/var/cache/rack/body',
  verbose: true
run app

# config/application.rb
config.action_dispatch.rack_cache = true
config.action_dispatch.rack_cache = {
  verbose: true,
  metastore: 'file:/var/cache/rack/meta',
  entitystore: 'file:/var/cache/rack/body'
}


require 'dalli'
require 'rack/cache'
use Rack::Cache,
  verbose: true,
  metastore: "memcached://localhost:11211/meta",
  entitystore: "membached://localhost:11211/body"
run app

require 'rack/cache'
use Rack::Cache,
  verbose: true,
  metastore: <any backend>
  entitystore: "noop:/"
run app

```

```
```

