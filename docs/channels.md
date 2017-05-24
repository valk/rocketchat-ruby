### Channels API

Channels are RocketChat's public rooms.

#### channels.create

```ruby
require 'rocketchat'

rocket_server = RocketChat::Server.new('http://your.server.address/')
session = rocket_server.login('username', 'password')
channel = session.channels.create('new_channelname',
                     members: ['username1', 'username2'])
```

Optional parameters for create are:

:members, :read_only, :custom_fields


#### channels.info

```ruby
require 'rocketchat'

rocket_server = RocketChat::Server.new('http://your.server.address/')
session = rocket_server.login('username', 'password')
channel = session.channels.info(name: 'some_channelname')
```

Either room_id (RocketChat's ID) or name can be used.


#### channels.list

_N.B. list is also used for searching/querying_

```ruby
require 'rocketchat'

rocket_server = RocketChat::Server.new('http://your.server.address/')
session = rocket_server.login('username', 'password')
channels = session.channels.list(query: {usernames: 'friend-username'})
```


### channels.rename

```ruby
require 'rocketchat'

rocket_server = RocketChat::Server.new('http://your.server.address/')
session = rocket_server.login('username', 'password')
channel = session.channels.info(name: 'some_channelname')
session.channels.rename(channel.id, 'new_channelname')
```