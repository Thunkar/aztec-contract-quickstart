# Setup

```bash
aztec-up
docker pull aztecprotocol/aztec:3.0.0-nightly.20251015
docker tag aztecprotocol/aztec:3.0.0-nightly.20251015 aztecprotocol/aztec:latest
```

NOTE: Make sure the versions of aztec libs on the `Nargo.toml` files matches the one pulled by the nightly tag!
NOTE (to self): Check how to pull specific nightlies, go an bother whomever needs to implement it if there's no way to do it. Pulling the docker images directly is hella hacky!

# Compilation

```bash
aztec-nargo compile (--package amm_contract/token_contract) && \
aztec-postprocess-contract
```

# Testing

```bash
aztec test --test-threads 5 (--package amm_contract/token_contract) (--exact mod_of_test::name_of_test)
```
