#1
import hashlib
import time

class Block:
    def _init_(self, index, previous_hash, data):
        self.index = index
        self.timestamp = time.time()
        self.data = data
        self.previous_hash = previous_hash
        self.hash = self.calculate_hash()

    def calculate_hash(self):
        return hashlib.sha256(f"{self.timestamp}{self.data}{self.previous_hash}".encode('utf-8')).hexdigest()
    
class Blockchain:
    def _init_(self):
        self.chain = [self.create_genesis_block()]

    def create_genesis_block(self):
        return Block(0, "0", "Genesis Block")

    def get_last_block(self):
        return self.chain[-1]
    
    def add_block(self, new_block):
        new_block.previous_hash = self.get_last_block().hash
        new_block.hash = new_block.calculate_hash()
        self.chain.append(new_block)

if  _name_ == '_main_':
    blockchain = Blockchain()

    # Add blocks to the blockchain
    block1 = Block(1, "", "Block 1 Data")
    blockchain.add_block(block1)
    
    block2 = Block(2, "", "Block 2 Data")
    blockchain.add_block(block2)

    block3 = Block(3, "", "Block 3 Data")
    blockchain.add_block(block3)

    # Print block chain details
    for block in blockchain.chain:
        print(f"Block: {block.index}")
        print(f"Timestamp: {block.timestamp}")
        print(f"Data: {block.data}")
        print(f"Previous Hash: {block.previous_hash}")
        print(f"Hash: {block.hash}")
        print(f"")

        #2
        // SPDX-License-Identifier: MIT
pragma solidity 0.8.24;
contract Store {
    uint value;
    function store() external view returns (uint){
        return value;
    }
}
#3
// SPDX-License-Identifier: MIT
pragma solidity 0.8.24;
contract Store {
    uint value;
    function store() external view returns (uint){
        return value;
    }
    function retrieve(uint values) external  {
        value -= values;
    }
}

#4
/ SPDX-License-Identifier: MIT
pragma solidity 0.8.24;
contract Helloworld {
    function myHelloworld() public pure returns (string memory){
        return "Hello World";
    }
}
#5
// SPDX-License-Identifier: MIT

pragma solidity 0.8.24;

contract Store {
    uint value = 10;
    function store() external view returns (uint){
        return value;
    }

    function retrive(uint _value) external {
        value = _value;
    }
}
#6
// SPDX-License-Identifier: MIT
pragma solidity 0.8.24;

contract Contract {
    uint public count = 0;
    event Increment(uint value);
    event Decrement(uint value);

    function getCount() view public returns(uint){
        return count;
    }

    function increment() public  {
        count += 1;
        emit Increment(count);
    }
    
    function decrement() public  {
        count -= 1;
        emit Decrement(count);
    }
}

#6
// SPDX-License-Identifier: UNLICENSED
// Solidity program to implement 
// Arithmetic Operators 
pragma solidity 0.8.24; 

// Creating Contract 
contract Arithmetic { 
	
    function arithmetic(uint a, uint b) public pure returns (uint, uint, uint, uint, uint, uint, uint) { 
    // Addition  
    uint sum = a + b; 
        
    // Subtraction  
    uint sub = a - b; 
        
    // Multiplication  
    uint mul = a * b; 
        
    // Division  
    uint div = a / b; 

    // Modulas
    uint mod = a % b;

    // Increment
    uint inc = ++a;

    // Decrement
    uint dec = --a;
        
    
    return (sum, sub, mul, div, mod, inc, dec); 
    } 
}
#7
pragma solidity 0.8.24;
contract Store{
    uint value;
    function store() external view returns(uint) {
      return value;  
    }
    function retrieve(uint _value)external{
      value=_value;
    }
}
#8
pragma solidity 0.8.24;
contract HelloWorld{
    function sayHelloWorld() public pure returns(string memory){
        return "Hello World";

    }
}
#9
pragma solidity 0.8.24;
contract Counter{
    uint public count=0;
    event Increment(uint value);
    event Decreament(uint value);
    function getcount() view public returns(uint){
        return count;
    }
    function increament() public{
        count+=1;
        emit Increment(count);
    }
    function decreament() public{
        count-=1;
        emit Decreament(count);
    }
}
#10
pragma solidity 0.8.24;

contract Bank{
    uint private Balance = 0;

    function viewBalance() public view returns(uint256){
        return Balance;
    }

    function deposit(uint256 amt)  public {
        Balance += amt;
        
    }
     function Withdraw(uint256 amt)  public {
        Balance -= amt;
        
    }
}
