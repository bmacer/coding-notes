17 mar 2021
- practiced with deploying an ethereum project to the rinkeby test network with infura io
- got exposed to nextjs, a wrapper around react that makes moving from pages easier

18 mar 2021
- got exposure to factory vs. primary interaction in front end
- got exposure to more nextjs, react, semantic-ui-react for front end dev
- read @lightclients's write-up on EIP-3074, which looks to decrease ETH cost by batching of sorts, allowing for a trusted "invoker" 

19 mar 2021
- family day

20 mar 2021
- practice with semantic-ui-react

21 mar 2021
- discovered "fractional" nft project, looks quite interesting, read up on discord

23 mar 2021
- endeavoring to work through the rust book
- worked through intro substrate tutorial

24 mar 2021
- thru chapter 4 of rust book (ownership and referencing)

25 mar 2021
- chapter 5 of rust book: structs, defining and instantiating, struct update syntax, tuple structs, :? and :#? specifiers, deriving Debug, implementing instance methods and helper functions
- 6.1 of rust book: basics of enum, defining and implementing, storing data in enum, different values, defining methods, and first intro to Option<T> 
- 6.2 match operator with enums, match with Option<T> to act only on existence, and the _ placeholder for catchall matching
- 6.3 if let for single-match cases (loses some thorough checking)
- 7.1 basics of package and crate (library and binary) definitions
- 7.2 modules and code tree structure
- 7.3 pub keyword
- 7.4 the use statement
- 7.5 splitting modules into different files
- 8.1 vectors, creating, pushing, accessing values, updating values
- 8.2 strings, combining strings, bytes, chars and grapheme clusters, slicing strings
- 8.3 HashMaps

26 mar 2021
- reviewed exercises related to ch 1-8 topics
- 9.1 panic!
- 9.2 Result<T, E>... will need to revisit a few more times
- 9.3 panic vs Result... build error checks into structs
- 10.1 generics in structs, enums, methods

27 mar 2021
- created a minute pull request on substrate doc :-)
- watched [video](https://www.youtube.com/watch?v=k4LFMcMSJVc) with dan shields.  lovely overview of the sales pitch for using substrate (modular and inter-operable chain-building
- watched [video](https://www.youtube.com/watch?v=47mL30nePLU) with dan forbes.  great for the community of web3/polkadot/multi-chain/decentralized life, particular with regards to community governance
- second run-through of [add a pallet to your runtime](https://substrate.dev/docs/en/tutorials/add-a-pallet/) tutorial for nicks pallet, played some
- first run-through of [build a poe decentralized application](https://substrate.dev/docs/en/tutorials/build-a-dapp/) tutorial for "owning" files.  really pretty awesome to see.
- pretty thorough run-through of [start a private network](https://substrate.dev/docs/en/tutorials/start-a-private-network/) which i got working, i think.  not sure why if i have four nodes and kill the origin node it doesn't stay up...what's the point i guess?  but perhaps those answers will come to light.

28 mar 2021
- first run-through of [Write a Pallet in its Own Crate](https://substrate.dev/docs/en/tutorials/create-a-pallet/).  pretty simple, nothing too fancy or interesting, just a structural discussion
 10.2 (rust book): traits and implementing them
- tried to get through the [hello world recipe](https://substrate.dev/recipes/runtime-printing.html), but it seems there's some versioning issues (using substrate 2.0, should be updated to 3.0).  i'm a bit new to figure that out, though i tried.  dependency hell.  will focus on tutorials and knowledge base for now.

29 mar 2021
- 10.3 lifetimes.  Just read, didn't code along
- read about IPFS, which is a distributed file sharing technology driven by hashing files, DAGs (hashing multiple files and folders and parts of files) and DHT (I think?  Distributed hashing table for finding your files.  This is libp2p).

30 mar 2021
- read through of forkless upgrade substrate tutorial.  Need to implement myself, seems straightforward.

31 mar 2021
- 11.1 in rust book, testing.  Just read, need to practice coding.
- 11.2 organizing tests
- 11.3 understanding how tests are run

1 apr 2021
- 12.1 cli tool command line input

2 apr 2021
- 12.2 reading a file
- 12.3 refactor early.  Super interesting.  Do this many times.

3 apr 2021
- went through 12.2 and 12.3 live
- worked through 12.4-12.6 live.  good practice, still need more

4 apr 2021
- 13.1 closures, pretty tough concept will need a fair amount of practice

5 apr 2021
- 13.1 closures, slow crawl through the code but worth it.  practiced with HashMaps, some testing, lots of compiling-and-failing.  Gained some understanding of structs, the where clause, "type"ing, certainly a bit on closures.

6 apr 2021
- 13.2 iterators.  Need to walk through slowly.  First touch.

7 apr 2021
- 13.3 improving io project.  Quick read, need practice

8 apr 2021
- first try getting rust to read and parse a zip file.  Rough times lol.  Will get there.

9 apr 2021
- 13.4 comparing performance iterator vs for

10 apr 2021
- ch 14 crates.io, publishing libs

11 apr 2021
- 15.1 using Box<T>

12 apr 2021
- 15.2 started (deref)

13 apr 2021
- revisited programming a guessing game (chapter 2)
- revisited [create first substrate chain](https://substrate.dev/docs/en/tutorials/create-your-first-substrate-chain/)
- found a couple video playlists to check out: (1) [polkadot technical explainers](https://www.youtube.com/playlist?list=PLOyWqupZ-WGuAuS00rK-pebTMAOxW41W8), (2) [blockchain fundamentals from web3](https://www.youtube.com/playlist?app=desktop&list=PLxVihxZC42nF_MCN9PTvZMIifRjx9cZ2J)
- watched [video 1](https://www.youtube.com/watch?v=y8YyZELnVaw&list=PLxVihxZC42nF_MCN9PTvZMIifRjx9cZ2J&index=1) of 20 of blockchain fundamentals.  interesting for the history of blockchain, and it's gradual (not instant) evolution, and the failed attempts from before.  the ideas of the double-spend problem, proof of work, proving order with hashing.

14 apr 2021
- revisited [importing nicks pallet](https://substrate.dev/docs/en/tutorials/add-a-pallet/) and [create a proof of existence application](https://substrate.dev/docs/en/tutorials/build-a-dapp/).  it continues to be a struggle to understand the Rust code, but i have a slightly better feel for it than i did before.  for example this is all levels of ugly

      pub trait Config: frame_system::Config {
          type Event: From<Event<Self>> + Into<<Self as frame_system::Config>::Event>;
      }
pub is public.  and we're configuring a trait, called Config, of the type Config as defined in frame_system.  and this trait has an Event type, which... i'm not sure...can be converted from itself into a base event?

TODOs:
- keep with some PRs for docs if they keep getting approved :-)
- keep up on discord chat for substrate doc
- keep up on discord chat for microNFT project
- keep reviewing stack overflow for substrate
- keep trudging through rust book and reiterating practice
- keep going through substrate tutorials
- check out substrate recipes
