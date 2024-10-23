# Diplodoc Static Template

### Confgure GitHub secrets

Enable GitHub pages, then your github action will start working

### Prepare develop your environment

```sh
rm -rf ./build/*
npx -y @diplodoc/cli -i ./ -o ./build
npx -y http-server ./build --port=5000 --host=0.0.0.0 --cors
```

After that, just open http://localhost:5000

### Docker

If you need to build docker, just run the code

```sh
rm -rf ./build/*
npx -y @diplodoc/cli -i ./ -o ./_site
DOCKER_BUILDKIT=1 docker build --platform linux/amd64 -t MYCOMPANY/docs .
docker push MYCOMPANY/docs:latest
```