## Stacks API Node easy start

Download this repo as a ZIP file and unzip it and use `cd <directory` in the Terminal to enter the folder.

To start a stacks API node you need to first install [Docker Desktop](https://www.docker.com/products/docker-desktop).

Once Docker Desktop is up and running ensure your environment is set up correctly by running the command
```
$ docker ps
```

At the beginning this should return the following or something like this
```
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
```

Once docker is installed and working clone this repository.

Run this command to create a volume where the PostgreSQL database will be persisted.
```
docker volume create postgres
```

Then run this command to bring up the `postgres` database, the `stacks-blockchain`, the `stacks-explorer` and the `stacks-blockchain-api` containers.

```
docker-compose up -d
```

This should return a result that looks like this:

```
Creating network "stacks-api-node_backend" with the default driver
Creating stacksnode_stacks-blockchain_1     ... done
Creating stacksnode_postgres_1          ... done
Creating stacksnode_stacks-blockchain-api_1 ... done
Creating stacksnode_stacks-explorer_1 ... done
```

The `stacks-blockchain` takes ~3 days to sync up to the blockchain.
Once sync is completed the API should be accessible at `http://localhost:3999`. Switch over your wallets to use this in their settings.

While sync is still in progress, after about 12 hours you should be able to see the blocks start to roll into in the explorer. Stacks Explorer should be accessible at `http://localhost:3099`
