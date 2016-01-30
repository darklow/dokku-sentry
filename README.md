# dokku-sentry
Sentry on dokku

## Prepare dokku

Go to your dokku server and install following plugins:

```
# Install official postgresql plugin
sudo dokku plugin:install https://github.com/dokku/dokku-postgres.git postgres

# Install official redis plugin
sudo dokku plugin:install https://github.com/dokku/dokku-redis.git redis

```

# Setup

```

# Create dokku app
ssh dokku@katana apps:create sentry


# Create postgresql db and link it to the app
ssh dokku@katana postgres:create sentry
ssh dokku@katana postgres:link sentry sentry

# Create redis instance and link it to the app
ssh dokku@katana redis:create sentry
ssh dokku@katana redis:link sentry sentry

# Add remote dokku
git remote add dokku dokku@katana:sentry

# Deply
git push dokku


```