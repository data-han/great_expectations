# Postgres Reference Environment

This reference environment spins up two containers:

- A postgres database pre-loaded with a sample of one month of NYC taxi trip data
- A jupyter notebook server

The jupyter notebook server contains a notebook with a quickstart for using Great Expectations with postgres.

You can connect to the database using the following credentials:

- Outside the container on your host machine: "postgresql://example_user@localhost/gx_example_db"
- Inside the notebook: "postgresql://example_user@db/gx_example_db"

Please note that unless you take steps to save data, your notebook and database changes could be lost when you stop the reference environment.

To copy data out of the container, you can use the `docker cp` command. For example to copy a notebook:

```bash
docker ps
```

`docker ps` will help you get the container id for use in the next command.

```bash
docker cp jupyter_container_id:/gx/my_notebook.ipynb .
```

Please also note that the database and jupyter notebook will use the default ports, so please make sure you don't have anything else running on those ports, or take steps to avoid port conflicts.
