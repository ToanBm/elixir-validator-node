## Update Elixir validator node to 3.4.7 (29.09.2024)
### Run 
```Bash
docker kill elixir
docker rm elixir
docker pull elixirprotocol/validator:v3
docker run --name elixir --env-file validator.env --platform linux/amd64 -p 17690:17690 --restart unless-stopped elixirprotocol/validator:v3
```
If successful:
```Bash
SOFTWARE VERSION: 3.4.7
BROKER: validator.testnet-3.elixirdev.xyz:9092
API URL: https://api.testnet-3.elixir.xyz
.......
```
