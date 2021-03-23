working through [create your first substrate chain](https://substrate.dev/docs/en/tutorials/create-your-first-substrate-chain/) tutorial.

nick pallet q:
- Cargo.toml <-- one change (this is actually two changes)
- fix "this is important to enable" -> "it is important to enable"
- quick mention what nicks pallet does
- Before moving on, check that the new dependencies resolve correctly by running: (add expected time/result)
- /// Already in your template for Ballances: (misspelled) https://substrate.dev/docs/en/tutorials/add-a-pallet/configure-a-pallet
- 

[install](https://substrate.dev/docs/en/knowledgebase/getting-started/)
- install and update brew
- brew install openssl cmake
- install and source rust (.cargo/env)
- compile wasm (nightly)
- config check (rustup show)

[set up computer](https://substrate.dev/docs/en/tutorials/create-your-first-substrate-chain/setup):
- go through installation steps
- compile substrate dev hub node template (git clone + cd + cargo build --release)
- install node and yarn
- set up front end template and yarn install
- note the output lines

[interacting with node](https://substrate.dev/docs/en/tutorials/create-your-first-substrate-chain/interact)
- start node template (./target/release/node-template --dev --tmp)
- start front-end (in front-end folder, yarn start opens http://localhost:8000/substrate-front-end-template)
- explore layout
- note built-in balances
- transfer some money to dave (looks like you can't transfer to alice/bob?)
- explore metadata
- explore pallet interactor (extrinsic=POST, query=GET, RPC/constant?)

[import nicks pallet](https://substrate.dev/docs/en/tutorials/add-a-pallet/import-a-pallet)
- atom edit the node folder
- edit runtime/Cargo.toml to include pallet-nicks as a dependency and pallet-nicks/std in features/std
- add nick parameter_types and implement (impl) in runtime/src/lib.rs
- add nick to construct_runtime! macro
- build (cargo build --release) and run (./target/release/node-template --dev --tmp)
- start the front-end
