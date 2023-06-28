# Getting Started with Cartesi Rollups 

## Requirements

- Docker (v20.10.23+) - Recommended to use docker desktop.
    - otherwise, also ensure [Buildkit](https://github.com/moby/buildkit) is available and 
    - QEMU support for desktop [placeholder link here](123)
    - please, just **install docker desktop**, you won't need to worry.
- Unix enviroment (MacOS, Linux or Windows+WSL2)
- Your IDE (VS Code recommended)

## Running your first example

### Echo Python
 
You don't need to follow any other instruction not cited here. Just trust me, bro. 

1) Clone the [examples repository](https://github.com/cartesi/rollups-examples/) 
 > git clone https://github.com/cartesi/rollups-examples.git

2) Open 2 shell terminals and follow this:

At **Terminal 1**, let's get the cartesi node running:

```bash
cd echo-python
# build your first docker image with the CM
docker buildx bake --load
# start the node with the image you just built
docker compose -f ../docker-compose.yml -f ./docker-compose.override.yml up
```

At **Terminal 2**, let's interact with it:
 
Here we are going to use `frontend-console` CLI shipped with the examples
```bash
cd frontend-console

#install and build the project dependencies
yarn 
yarn build 

# send your first input/transaction to the node
yarn start input send --payload "Hey gbarros/awesome-cartesi really works"

#then wait for a few seconds for the transaction to be processed
# you can check the logs on the Terminal_1

#check for new notices created with your last input
yarn start notice list
```

🥳🎉 you just built and run your first example code on Linux VM Rollups!