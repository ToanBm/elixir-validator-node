## Update Elixir validator node to 3.4.9
### Run 
```Bash
docker ps -a | grep elixirprotocol | awk '{print $1}' | xargs docker stop
```
```Bash
docker ps -a | grep elixirprotocol | awk '{print $1}' | xargs docker rm
```
```Bash
docker pull elixirprotocol/validator:v3 --platform linux/amd64
```
```Bash
docker run --name elixir --env-file validator.env --platform linux/amd64 -p 17690:17690 --restart unless-stopped elixirprotocol/validator:v3
```
### Check log
```Bash
docker logs elixir -n 100 -f
```
---------------------------------------------------------------------------------------------------------
## Install Elixir validator node
### Download 
```Bash
docker pull elixirprotocol/validator:v3
```
```Bash
nano validator.env
```
```Bash
ENV=testnet-3

# Allowed characters A-Z, a-z, 0-9, _, -, and space
STRATEGY_EXECUTOR_DISPLAY_NAME=your-name
STRATEGY_EXECUTOR_BENEFICIARY=your-wallet
SIGNER_PRIVATE_KEY=your-private-key

```
### Start 
```Bash
docker run --name elixir --env-file validator.env --platform linux/amd64 -p 17690:17690 --restart unless-stopped elixirprotocol/validator:v3
```
### Check log
```Bash
docker logs elixir -n 100 -f
```

## Done!

