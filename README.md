# English README　[Jump to Japanese Version](#japanese)

# Preview
For an easy interaction with the contract use abi.ninja website.
Here is a link to the contract loaded on it: [FundMe contract]()

Click on function on the left to add them in the center of the page and interact with them.
- Functions under the 'READ' category are for getting actual values.
- Functions under the 'Write' category are for inserting new data.

- NOTE: The above contract is deployed on the Sepolia Testnet, so testnet funds are required for interacting with it.


# Foundry Fund Me

Contract is deployed at xxxx
[View on Sepolia]()

It is a contract used for sending funds to it. And then withdraw funds.
It is efficient enough for learning foundry basics and contract interaction when it comes to money transfer.

I used the 32 hours long video from Cyfrin Foundry Blockchain course to learn about Foundry.  
[Cyfrin Foundry](https://github.com/Cyfrin/foundry-full-course-f23)


## Requirements

- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
  - You'll know you did it right if you can run `git --version` and you see a response like `git version x.x.x`
- [foundry](https://getfoundry.sh/)
  - You'll know you did it right if you can run `forge --version` and you see a response like `forge 0.2.0 (816e00b 2023-03-16T00:05:26.396218Z)`


## Quickstart

```
git clone https://github.com/Jer-B/Foundry_FundMe
cd Foundry_FundMe
forge build
```

# Usage

Deploy:

```
forge script scripts/DeployFundMe.s.sol
```

## Testing Methods

1. Unit
2. Integration
3. Forked
4. Staging

In this repo we cover test number #1 and #3. 


```
forge test
```

or 

```
forge test --match-test testFunctionName
```
Don't forget to change the `testFunctionName` above for the actual test function you want to test. (look at functions from files in the `test` folder)

or

```
forge test --fork-url $alchemy_RPC_sepolia
```

### Test Coverage

```
forge coverage
```


# Deployment to a testnet or mainnet

1. Setup environment variables

You'll want to set your `alchemy_RPC_sepolia` and `PRIVATE_KEY_TESTNET` as environment variables. You can add them to a `.env` file, similar to what you see in `.env.example`.

- `PRIVATE_KEY_TESTNET`: The private key of your account (like from [metamask](https://metamask.io/)). **NOTE:** FOR DEVELOPMENT, PLEASE USE A KEY THAT DOESN'T HAVE ANY REAL FUNDS ASSOCIATED WITH IT.
  - You can [learn how to export it here](https://metamask.zendesk.com/hc/en-us/articles/360015289632-How-to-Export-an-Account-Private-Key).
- `alchemy_RPC_sepolia`: This is url of the sepolia testnet node you're working with. You can get setup with one for free from [Alchemy](https://alchemy.com/?a=673c802981)

Optionally, add your `ETHERSCAN_API_KEY` if you want to verify your contract on [Etherscan](https://etherscan.io/).

1. Get testnet ETH

Head over to [faucets.chain.link](https://faucets.chain.link/) and get some testnet ETH. You should see the ETH show up in your metamask.

3. Deploy

```
forge script script/DeployFundMe.s.sol --rpc-url $alchemy_RPC_sepolia --private-key $PRIVATE_KEY_TESTNET --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY
```

## Scripts

After deploying to a testnet or local net, you can run the scripts. 

Using cast deployed locally example: 

```
cast send <FUNDME_CONTRACT_ADDRESS> "fund()" --value 0.1ether --private-key <PRIVATE_KEY>
```

or
```
forge script script/interactions.s.sol --rpc-url $alchemy_RPC_sepolia --private-key $PRIVATE_KEY_TESTNET  --broadcast
```

### Withdraw

```
cast send <FUNDME_CONTRACT_ADDRESS> "withdraw()"  --private-key <PRIVATE_KEY_TESTNET>
```

## Estimate gas

You can estimate how much gas things cost by running:

```
forge snapshot
```

And you'll see an output file called `.gas-snapshot`


# Formatting


To run code formatting:
```
forge fmt
```

<a name="japanese"></a>
# 日本語版のREADME

# プレビュー
コントラクトとの簡単な対話には abi.ninja ウェブサイトを使用してください。
以下は、それにロードされたコントラクトへのリンクです: [FundMe contract]()

左側の関数をクリックして、それらをページの中央に追加し、それらと対話します。
- `READ`カテゴリーの下にある関数は実際の値を取得するためのものです。
- `Write`カテゴリーの下にある関数は新しいデータを挿入するためのものです。

- 注意: 上記のコントラクトは Sepolia テストネット上にデプロイされており、それと対話するにはテストネット用の資金が必要です。

# Foundry  FundMe

このコントラクトは、0xxxx にデプロイされています。
[Sepoliaで表示]()

これは、資金を送金し、その後資金を引き出すために使用する契約です。
資金の送金に関するFoundryの基本とコントラクトの相互作用を学ぶには効率的です。

Foundryを学ぶために、Cyfrin Foundry Blockchainコースの32時間の長いビデオを使用しました。
[Cyfrin Foundry](https://github.com/Cyfrin/foundry-full-course-f23)

## 必要条件

- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
  - git --version を実行して git version x.x.x のような応答が表示されれば成功です。
- [foundry](https://getfoundry.sh/)
  - forge --version を実行して forge 0.2.0 (816e00b 2023-03-16T00:05:26.396218Z) のような応答が表示されれば成功です


## クイックスタート

```
git clone https://github.com/Jer-B/Foundry_FundMe
cd Foundry_FundMe
forge build
```


## 使用方法

デプロイメント:

```
forge script scripts/DeployFundMe.s.sol
```

## テスト方法

1. ユニットテスト
2. 統合テスト
3. フォークテスト
4. ステージングテスト

このリポジトリではテスト番号1と3をカバーしています。


```
forge test
```

or 

```
forge test --match-test testFunctionName
```
上記の testFunctionName を実際にテストしたいテスト関数の名前に変更しないでください。(test フォルダ内のファイルから関数を参照してください)

or

```
forge test --fork-url $alchemy_RPC_sepolia
```

### テストカバレッジ

```
forge coverage
```


# テストネットまたはメインネットへのデプロイ

1. 環境変数の設定

`alchemy_RPC_sepolia` と `PRIVATE_KEY_TESTNET` を環境変数として設定する必要があります。これらを .env ファイルに追加することができます。.env.example に示されているようなものです。


- `PRIVATE_KEY_TESTNET`: アカウントのプライベートキー[metamask](https://metamask.io/)). **注意**: 開発のために、実際の資金が関連付けられていないキーを使用してください。

  - [ここでキーのエクスポート方法を学ぶことができます](https://metamask.zendesk.com/hc/en-us/articles/360015289632-How-to-Export-an-Account-Private-Key).
- `alchemy_RPC_sepolia`: これはあなたが作業している Sepolia テストネットノードのURLです。 [Alchemy](https://alchemy.com/?a=673c802981)　から無料でセットアップできます。

オプションで、 [Etherscan](https://etherscan.io/)　で契約を検証したい場合は ETHERSCAN_API_KEY を追加してください。

1. テストネットETHを取得

 [faucets.chain.link](https://faucets.chain.link/) にアクセスし、テストネットETHを取得してください。MetamaskでETHが表示されるはずです。

3. デプロイ

```
forge script script/DeployFundMe.s.sol --rpc-url $alchemy_RPC_sepolia --private-key $PRIVATE_KEY_TESTNET --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY
```

## Scripts

テストネットまたはローカルネットワークにデプロイした後、スクリプトを実行できます。

ローカルにデプロイされたキャストを使用する例:

```
cast send <FUNDME_CONTRACT_ADDRESS> "fund()" --value 0.1ether --private-key <PRIVATE_KEY>
```

or
```
forge script script/interactions.s.sol --rpc-url $alchemy_RPC_sepolia --private-key $PRIVATE_KEY_TESTNET  --broadcast
```

### 資金を引き出す

```
cast send <FUNDME_CONTRACT_ADDRESS> "withdraw()"  --private-key <PRIVATE_KEY_TESTNET>
```

## ガス代確認


```
forge snapshot
```

`.gas-snapshot` という名前の出力ファイルが表示されます


# フォーマット


コードのフォーマットを実行するには：
```
forge fmt
```
