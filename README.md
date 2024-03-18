## Developer setup
The app has two distinct components, the Go backend and the VueJS frontend. In the dev environment, both are run independently.

## Pre-requisites
- go
- nodejs (if you are working on the frontend) and yarn
- Postgres database

### First time setup
git clone https://github.com/arcabLTD/newsletter-go.git. The project uses go.mod, so it's best to clone it outside the Go src path.

Copy `config.toml.sample` as `config.toml` and add your config.

```bash
make dist
```

to build the listmonk binary. Once the binary is built, run 

```bash
./listmonk --install 
```

to run the DB setup. For subsequent dev runs, use 

```bash
make run
```

### Running the dev environment

Run `make run` to start the listmonk dev server on :9000.

Run `make run-frontend` to start the Vue frontend in dev mode using yarn on :8080. All /api/* calls are proxied to the app running on :9000. Refer to the frontend README for an overview on how the frontend is structured.

Visit http://localhost:8080