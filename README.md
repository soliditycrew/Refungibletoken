# Refungibletoken
Value of an ERC20 backed by the value of a NFT

Steps to create:

npm install -g truffle - in current directory

npm truffle init . - Creates basic truffle project in current directory

Change version of solidity in truffle-config.js for the compiler

Install openzeppelin:
 - npm install -y (installs without asking questions)
 - npm install @openzeppelin/contracts@3.2.1-solc-0.7

Create RefungibleNFT contract in Contract folder - touch contracts/refungibletoken.sol 
Open file refungiblenft.sol

//Specify solidity version
pragma solidity ^0.7.3

//import the librarys that the contract will reference

import '@openzeppelin/contrats/token/ERC721/IERCE721.sol'; //NFT token standard interface
import '@openzeppelinopenzeppelin/contrats/token/ERC20/IERC20.sol'; //ERC20 Standard token interface
import '@openzeppelinopenzeppelinopenzeppelin/contrats/token/ERC20/ERC20.sol'; // ERC20 standard token contract implementation

contract refungibletoken is ERC20 { //ERC20 is defined in openzeppelin library
  uint public icoSharePrice; //sets the price per share of the NFT
  uint public icoShareSupply; //The amount of shares available
  uint public icoEnd; //limited in time
  
  uint public nftID; //identify the NFT, by specifying the ID
  IERC721 public nft;
  IERC20 public dai;
  
address public admin; //address of the id, who buys the NFT and sends to the refungibleNFT 
  
constructor( // constructor function for defining the smart contract with arguments when the function is called to deploy the smart contract
  string memory _name,
  string memory _symbol,
  address _nftAddress,
  uint _nftId,
  uint _icoSharePrice,
 )
 ERC20(_name, _symbol)
 {
  nftID = _nftID;
  nft = IERC721(_nftAddress);
  icoSharePrice = _icoSharePrice;
  icoShareSupply = _icoShareSupply;
  dai = IERC20(_daiaddress);
  admin = msg.sender;
  }
  
  function startIco() external {
  }
  
  
 
}


