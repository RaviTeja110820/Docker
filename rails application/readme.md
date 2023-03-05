# some changes

## edit this in  database.yml file

default: &default
  adapter: mysql2
  encoding: utf8mb4
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
# username: root
# password: mysql@123
  username: <%= ENV['DB_USER'] %>
  password: <%= ENV['DB_PASSWORD'] %>
  host: <%= ENV['DB_HOST'] %>
  socket: /var/run/mysqld/mysqld.sock

development:
  <<: *default
# database: SampleApp_development
  database: <%= ENV['DB_NAME'] %>


## you can also refer to this below link 

<https://medium.com/@satriajanaka09/introduction-to-dockerizing-your-ruby-on-rails-application-73747ecf9de5>