# market_fee_contract

## contract

dev endpoint: `http://18.180.227.173:8545/`

### nftRight `0x2C29DB05ec2276c225C177Aea9270168D22b2c2B`
合约

**Function**

- contractorMint(address[] , uint256[], address[]):管理员批量mint Nft给项目方
    * address[]:项目方的地址
    * uint256[]:NFT Tokenid
    * address[]:NFT Tokenid交易 对应的支付币种地址，若是原始币种则传address(0)

- transferContractor(address, uint256):项目方transfer NFT给别人
    * address: 接收方地址
    * uint256: tokenId

- contractorMintTo(address[], uint256[], uint256[]):项目方批量mint Nft给下线
    * address[]: 接收者地址
    * uint256[]: nft tokenid
    * uint256[]: 数量
  
- depositFee(uint256[], uint256[], address[]):管理员批量存手续费 payable函数
    * uint256[]: 存入手续费数量
    * uint256[]: 存入Nft Tokenid
    * address[]: tokenId对应的支付币种地址，若是原始币种则传address(0)

- claim(
        address,
        address,
        uint256,
        uint256,
        bool,
        uint8,
        bytes32,
        bytes32 
    )：提币
    * address:token地址（原生币种则传地址0）
    * address:提币账户地址
    * uint256:提币数量
    * uint256:nonce
    * bool:是否是原始币种（true则是，false不是）
    * uint8:v
    * bytes:r
    * bytes:s
  
**Event**

```solidity
    event SetURI(address add, string newUri);
    event ContractorMint(address[] receiver, uint256[] tokenId, address[] token);
    event ContractorMintTo(
        address[] receiver,
        uint256[] tokenId,
        uint256[] num
    );
    event DepositFee(uint256[] fee, uint256[] tokenId, address[] token);
    event Claim(address token, address account, uint256 number);
    event TransferContractor(
        address contractor,
        address receiver,
        uint256 tokenId
    );
```
