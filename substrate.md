working through [create your first substrate chain](https://substrate.dev/docs/en/tutorials/create-your-first-substrate-chain/) tutorial.

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
