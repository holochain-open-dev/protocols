# Dna Property: Progenitor

## Proposal

- Dna properties with this shape:

```rust
#[derive(Serialize, SerializedBytes, Deserialize, Clone, Debug)]
struct DnaProperties {
    progenitors: Vec<AgentPubKeyB64>,
}
```

- Progenitors agents cannot be revoked: they are progenitors throughout the lifetime of the Dna.

## Reasonale

- Having the agents identified by `AgentPubKeyB64`: strings are more easily configured and input from both UI and `.yaml` files.
- Having a `Vec<_>` of agents: having a vector of progenitor agents makes it so that we don't depend on only one agent to maintain the DHT stable.
- Preventing the progenitors from being revoked: revokation of progenitor privileges would be a clear source of non-determinism. In this case, it's always better to clone the Dna with a new progenitor address.

## Existing implementations

- [membrane_roles](https://github.com/holochain-open-dev/membrane-roles/blob/main/zome/zomes/membrane_roles/src/progenitor.rs#L5)
- [peer-share](https://github.com/holochain-in-action/peer-share/blob/main/holo-layer/zomes/peershare/src/helpers/progenitor.rs)