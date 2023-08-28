Suggestions and tips for Cartesi Rollups



## Better alias
We need to use docker commands all the time, in order to save time and avoid mistakes, we can create aliases for the base of the commands.

```bash
alias ctsi="docker compose -f ../docker-compose.yml -f ./docker-compose.override.yml"
# use this for host-mode
alias ctsi-host="docker compose -f ../docker-compose.yml -f ./docker-compose.override.yml -f ../docker-compose-host.yml"
```

you can also add it to your `.bashrc` or `.zshrc` file to make it permanent. Just also add
```bash
export ctsi
export ctsi-host
```

Now you can do `ctsi up` or `ctsi down` to start and stop the node, respectively.
