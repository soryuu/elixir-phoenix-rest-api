# Elixir Phoenix Rest API


## Development

Cloning this project:

```bash
git clone git@github.com:maxcnunes/elixir-phoenix-rest-api.git rest_api
```

### Running Locally

To start your Phoenix app:

  1. Install dependencies with `mix deps.get`
  1. Set the env variable `DATABASE_URL="ecto://user:password@db/rest_api_dev"` (you may change the values)
  1. Create and migrate your database with `mix ecto.create && mix ecto.migrate`
  1. Start Phoenix endpoint with `mix phoenix.server`

Now you can visit [`localhost:4000`](http://localhost:4000) from your browser.

### Running With Docker

  1. Create and migrate your database with `docker-compose run --rm local sh -c "mix ecto.create && mix ecto.migrate`
  1. Start Phoenix endpoint with `docker-compose run --rm local`

Now you can visit `<container-ip>:<container-public-port>` from your browser.
Or in case your are using [dockito-proxy](https://github.com/dockito/proxy) [api.local.dockito.org](api.local.dockito.org).


### Example requests with CURL

**List**
```bash
curl http://api.local.dockito.org/posts
```

**Create**
```bash
curl -H "Content-Type: application/json" \
     -X POST \
     -d '{"post": {"title":"Title 001","content":"Content 001"} }' \
     http://api.local.dockito.org/posts
```

**Update**
```bash
curl -H "Content-Type: application/json" \
     -X PUT \
     -d '{"post": {"title":"Title 001 Updated","content":"Content 001 Updated"} }' \
     http://api.local.dockito.org/posts/1
```

**Delete**
```bash
curl -X DELETE \
     http://api.local.dockito.org/posts/1
```

## Test

### Testing Locally

```shell
mix test
```

### Testing With Docker

```shell
docker-compose run --rm test
```
