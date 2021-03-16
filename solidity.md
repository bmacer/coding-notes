setup steps (local, after creating on remix):
- npm init
- npm install --save ganache-cli mocha solc fs-extra web3[@1.0.0-beta.35]
- create etheruem folder
- create compile.js file
- create deploy.js file
- create contracts folder and contract .sol file(s)
- copy in contract

compile file:
- check licensing line is in .sol file: // SPDX-License-Identifier: MIT
- require path, solc, fs
- get ref to build dir (path.resolve)
- delete folder and contents (fs.removeSync)
- get path to contracts folder (path.resolve)
- read file (fs.readFileSync w utf8)
- define input (see below #1)
- compile (solc.compile)
- recreate build folder (fs.ensureDirSync)
- iterate through to write files to build dir (fs.outputJsonSync(path..., contract)) (see below #2)

#1

    const input = {
      language: 'Solidity',
      sources: {
        'Rps.sol': {
          content: source
        }
      },
      settings: {
        outputSelection: {
          '*': {
            '*': ['*']
          }
        }
      }
    }
    
#2

    const compiled = solc.compile(JSON.stringify(input))
    contracts = JSON.parse(compiled).contracts;

    for(let fn of Object.keys(contracts)) {
      for(let con of Object.keys(contracts[fn])) {
        //let bytecode = contracts[fn][con].evm.bytecode.object;
        fs.outputJsonSync(
          path.resolve(__dirname, "build", `${con.replace(":", "")}.json`),
          JSON.stringify(contracts[fn][con])
        )
      }
    }

test file:
- update package.json ("test": "mocha")
- create test folder
- create test files
- require assert, ganache-cli, web3
- instantiate web3 with ganache provider
- require built json files
- declare vars
- beforeEach: get accounts
- beforeEach: build factory (web3.eth.Contract(parsed_interface).deploy({data:bytecode}).send({from/gas})) [[see #3]]
- build describe -> it tests

#3

    beforeEach( async () => {
      accounts = await web3.eth.getAccounts();
      factory = await new web3.eth.Contract(jsonCompiledFactory.abi)
        .deploy({
          data: jsonCompiledFactory.evm.bytecode.object,
          // arguments: [10, accounts[0]]
        })
        .send(  {
          from: accounts[0],
          gas: "3000000",
        });
    })

TODO deploy file:


fix new compiler issue:

    https://stackoverflow.com/questions/53353167/npm-solc-assertionerror-err-assertion-invalid-callback-specified

add license identifier:

    // SPDX-License-Identifier: MIT

what variable comes built in to the Contract, for retrieving address?

    msg
how do you get the address of the person in question?

    msg.sender
declare a string myString that anyone can see

    string public myString
basic error check for payment

    require(msg.value) > ...
marking for function involving payment

    payable
what does solidity use that is similar to classes in other languages

    struct
reusable tool for, for example, locking down access

    modifier
create a new instance of a "Car" object (don't forget the ...)

    Car car = new Car({})
    ...squigglies on the inside of the parens...
options to modify a variable to act as reference vs. full-copy in-memory

    storage | memory
solidity maps vs. js maps differences

    there is no key list, no values list, only look-ups, and all values exist (no undefined)
define a mapping

    mapping(address => bool) public votingRecords;
send money to someone (address is ad)

    ad.send(web3.utils.toWei("0.1", "ether"));
    ad.send(0.1 * 10**-18);
    ad.transfer(address(this).balance);
factory example

    contract GameFactory {
        address[] public deployedGames;

        function createRPS(uint wager) public {
            address game = new RockPaperGame(wager, msg.sender);
            deployedRPS.push(game);
        }

        function getActiveGames() public view returns (address[]) {
            return deployedGames;
        }
    }

    contract Game {...}
