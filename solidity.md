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
