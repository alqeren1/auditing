# Auditing with Slither, echidna


## to download docker:
yarn toolbox

## Docker test:
(fuzztest, for finding contract passwords stored onchain, bruteforce attack)

echidna /src/contracts/test/FuzzTest.sol --contract FuzzTest --config /src/contracts/test/config.yaml

## Always check these

Two most common attacks:
- Reentrancy
- Oracle Manipulation
Stay away from centralised oracles for price infos.

Before you deploy anything:
- Run Slither
- Look MANUALLY for oracle manipulation examples or reentrancy attack

```shell
yarn slither //to do a vulnerability test on contracts in ./contracts
solc-select use "0.8.7" //to change versions. It should be the same with .sol files
```
