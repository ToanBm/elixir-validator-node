## Update Elixir validator node to 3.4.7 (29.09.2024)
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
