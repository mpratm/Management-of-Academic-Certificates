// SPDX-License-Identifier: MIT

pragma solidity ^0.8.7;

//@author martiprat.mp@gmail.com

contract Certificates {
    
    mapping (bytes32 => address) private certificates;
    address private owner;
    address private Contract_Logic;


    /* Modifier "onlyOwner": condition for the functions that only the owner of the contract can execute the function that we are calling */
    modifier onlyOwner {
        require (msg.sender == owner);
        _;
    }

    /* Modifier "onlyContractLogic: condition for the functions that only the address with persmisions can execute the function that we are calling */
    modifier onlyContractLogic {
        require (msg.sender == Contract_Logic);
        _;
    }

    constructor() {
        owner = msg.sender;
    }

    function setOwneroftheContract(address _setOwner) public onlyOwner {
        owner = _setOwner;
    }

    function getOwneroftheContract() public view returns(address) {
        return owner;
    }

    function setContract_Logic(address _Contract_Logic) public onlyOwner {
        Contract_Logic = _Contract_Logic;
    }

    function getContract_Logic() public view returns(address) {
        return Contract_Logic;
    }

    function addCertificate(bytes32 _idCertificate, address _sender) public onlyContractLogic {
        certificates[_idCertificate] = _sender;
    }

    function getCertificates(bytes32 _idCertificate) public view onlyContractLogic returns (address) {
        return certificates[_idCertificate];
    }

}
