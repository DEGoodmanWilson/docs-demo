# Ruby SDK for user monitoring

***

Sqreen [protects your application users against major threats](doc:protect-your-users), such as account takeover, password bruteforce, suspicious activities coming from TOR or unusual VPN.

Sqreen supports [Devise framework](https://github.com/plataformatec/devise), out of the box, for automatic User Context. 

**Advanced User Context** allows you to set up user monitoring in your application with flexibility and powerful additional features. You will need to integrate Sqreen SDK in your application (< 10 minutes).

!!! success "Feature available in Ruby for Sqreen > 1.1.0"
    This SDK is available for versions of sqreen gem after `1.1.0`.

# User monitoring SDK

Two lines are enough to monitor your users activities with Sqreen.

Calls to `Sqreen.auth_track` should be performed when creating your user session, basically at **signup**, and **login**.

```ruby
require 'sqreen'
Sqreen.auth_track(is_login_successful, email: user.email)
```

!!! warning Sqreen integration at signup and login"
    You should **not** call `Sqreen.auth_track` each time you check a user session in your application.

Here is an example of a full implementation:

```ruby
require 'sqreen'

class SessionsController < ApplicationController
  def create
    user = login(params[:email], params[:password])
    Sqreen.auth_track(!user.nil?, email: params[:email])                 
    # ....
  end
end
```

# auth_track function

`auth_track` takes two positional arguments:

```ruby
def auth_track(success, user_identifiers)
```

1. The first argument is a **boolean** indicating if the login/signup attempt was successful or not (True or False).

2. The second argument is a **Hash** with your user identification information. They will be used on Sqreen's user interface to help you identify which users are at risk, or which are attacking your application. The hash keys and values should only be strings. 

# User identification

If your users can be identified with a single value (email, nickname...), you can send proceed that way:

```ruby
Sqreen.auth_track(true, email: user.email)
```

If your users are identified with a *composite primary key* (multiple values), all of them should be sent in order to identify them accurately on Sqreen's user interface. 

For example, if you are a white label shop and your users are identified by their email and the shop id, you can send these identifiers like this:

```ruby
Sqreen.auth_track(true, email: user.email, platform_id: platform.id)
```

!!! warning "Sqreen SDK only accepts user identifiers"
    Don't send any other information (like the auth failure reason). Sqreen will consider them as part of the user identifier, and will not be able to merge successful and failed authentications.