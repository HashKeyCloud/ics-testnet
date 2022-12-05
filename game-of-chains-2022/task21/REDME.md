# Task 21

## mission details
In the game-of-chains-2022 test event, there is task 21. The task requires validators to run relay nodes to complete 500 relay transactions. In order to verify the completion, the block height needs to be submitted.

In order to accomplish this task, HashQuark validators set up a relay node between the provider and the consumer chain, and initiate relay transactions. Here are the addresses where the relayed transaction takes place:
- provider：cosmos1zqf2pls7yctw984f0lem68tjcg0vp44f6yfzxk
- apollo：cosmos1sde9mq3ykkvs2my4fryzcgckh7dlljgz5g5ztj
- sputnik：cosmos17fnep9zp3qe9rn6t7nn69rhresk8u7ts089hay
- hero 1：cosmos14m4qf4zwvhhfvwmzgkth9ympnqx5wsx5ppsayw
- neutron：neutron1pvng67cekyf7hjquy8uw0vy83s9xhr063ke5l6

HashQuark queries the block height and transaction hash of the relay transaction through the following commands
```shell
gaiad query txs --events "message.sender=cosmos1zqf2pls7yctw984f0lem68tjcg0vp44f6yfzxk" --page 1 --limit 100 -o json | jq -r '.txs[].height ,.txs[].txhash'
```

In order to prove that 500 transactions have been relayed, HashQuark has queried 600 transactions stored in https://github.com/HashQuark-Research1/ics-testnet/tree/main/game-of-chains-2022/task21/ibcTxByHashQuark. xlsx. Include the block height and transaction hash of each transaction in the file.

