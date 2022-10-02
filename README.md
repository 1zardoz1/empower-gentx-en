<h1 align="center">EmpowerChain</h1>

![192093493-67779857-653e-4018-8c78-49530690f7a0](https://user-images.githubusercontent.com/100621008/193432234-78f7b5c3-2e22-4a1e-9ac2-f566bd52cd69.png)
**Prepare testnet altruistic-1**

*We will install and update the necessary packages*
```
sudo apt update && sudo apt upgrade -y && \
sudo apt install curl tar wget clang pkg-config libssl-dev jq build-essential bsdmainutils git make ncdu gcc git jq chrony liblz4-tool -y
```
*Installing Go 1.18.3*
```
cd $HOME && version="1.18.3" && \
wget "https://golang.org/dl/go$version.linux-amd64.tar.gz" && \
sudo rm -rf /usr/local/go && \
sudo tar -C /usr/local -xzf "go$version.linux-amd64.tar.gz" && \
rm "go$version.linux-amd64.tar.gz" && \
echo "export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin" >> $HOME/.bash_profile && \
source $HOME/.bash_profile && \
go version
```
*Install binary empowerd*
```
cd $HOME && git clone https://github.com/empowerchain/empowerchain && \
cd empowerchain/chain && \
make install && \
empowerd version --long | head
```
*Enter your node name in the moniker section ( < > ) remove it as well*
```
empowerd init <MONIKER> --chain-id altruistic-1 && \
empowerd config chain-id altruistic-1
```
*Replace wallet name with your wallet name and remove ( < > ) as well*
```
empowerd keys add <WALLET_NAME>
```
*Create a genesis account, enter your wallet name in <walletname> and remove ( < > ) as well*
  
*:warning:Save the secret words of your wallet:warning:*
```
empowerd add-genesis-account <WALLET_NAME> 1000000umpwr
  ```
*Create gentx*
  
*Look carefully at the section below and enter your information*
  ```
  empowerd gentx WALLET_NAME 1000000umpwr \
--chain-id=altruistic-1 \
--moniker="MONIKER" \
--commission-max-change-rate 0.1 \
--commission-max-rate 0.2 \
--commission-rate 0.05 \
--pubkey $(empowerd tendermint show-validator) \
--website="enter your own information" \
--security-contact="enter your email" \
--identity="enter your own information" \
--details="enter your own information"
 ```
*This will be the output you will get and you will get your gentx by putting <cat> in front of it*
 ![8](https://user-images.githubusercontent.com/100621008/193432937-a4af4dc3-f81e-4114-b3ce-7e9c4919b272.jpg)
  
 ![9](https://user-images.githubusercontent.com/100621008/193432945-32a74deb-f56c-41c1-9f98-76ba3492632f.jpg)
  
*Save the code you get somewhere, fork Empowerchain*
 ![1664667940692](https://user-images.githubusercontent.com/100621008/193433068-e9ffad6c-5752-4b82-b94f-b716536e0182.jpg)
*After clicking Add file and then clicking Creat New File, we paste the gentx code that we noted in the window that opens*
![1664667940697](https://user-images.githubusercontent.com/100621008/193433245-b30b26b7-adb0-44ea-b729-0f71c3c2c591.jpg)
  
![1664667940687](https://user-images.githubusercontent.com/100621008/193433251-8a72be88-5fcf-46dd-8d74-4051d2ab7926.jpg)
  
![14](https://user-images.githubusercontent.com/100621008/193433339-3d43e9f2-20cc-45c2-9601-7c29c35e61f9.jpg)
  
![1664667940681](https://user-images.githubusercontent.com/100621008/193433356-5dd5713a-6f00-4b07-8b3c-75398a3efd27.jpg)

  


