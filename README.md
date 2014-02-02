Railscast sm-rc237
===================
Dynamic attr_accessible
```
If want to change attributes based on say user permission and there is need of this.. as attributes are hardcoded in rails.
```

git clone
```
git clone 'https://github.com/sweetymehta/sm-rc237.git'

```
database setup
```
rake db:create
rake db:migrate
rails g devise:install
rails g bootstrap:install
rails g simple_form:install
rake db:seed
```
scaffold
```
#todo
rake db:migrate
rails g bootstrap:themed orders -f
rails g devise model_name
````
add admin as new field in user model
```
rails g migration add_admin_to_user admin:boolean
that will define for your post resource capability
```
And change sanitized params to include admin as fields
```
devise_parameter_sanitizer.for(:sign_up) << :admin          for sign_up
devise_parameter_sanitizer.for(:account_update) << :admin   for editing profile
```
check if current_user is admin or not
```
see post controller
params[:post].delete(:important) unless current_user.admin?
```
Rails Server
```
rails s
```
Rails Console
```
rails c
```
