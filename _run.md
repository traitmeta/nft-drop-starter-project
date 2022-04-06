# CMD

- yarn install --cwd ../metaplex/js/

- ts-node ../metaplex/js/packages/cli/src/candy-machine-v2-cli.ts --version

- 上传图片到AR
  `ts-node ../metaplex/js/packages/cli/src/candy-machine-v2-cli.ts upload -e devnet -k ~/.config/solana/id.json -cp config.json ./assets`

    ```text
    Beginning the upload for 3 (img+json) pairs
    started at: 1649230100820
    initializing candy machine
    initialized config for a candy machine with publickey: ACZJrTetuUQJDKZ8BJ82tM9EGM3xGwfTYMz7YhSWXZUs
    Uploading Size 3 { mediaExt: '.jpeg', index: '0' }
    Processing asset: 0
    Processing asset: 1
    Processing asset: 2
    Writing indices 0-2
    Done. Successful = true.
    ended at: 2022-04-06T07:29:26.064Z. time taken: 00:01:05
    ```

- 糖果机验证图片已经上传
`ts-node ../metaplex/js/packages/cli/src/candy-machine-v2-cli.ts verify_upload -e devnet -k ~/.config/solana/id.json`

    ```text
    wallet public key: 3nMgt92NgkxkACwq7UjEL8CtuF9M6HV5SmY1awc3mSRf
    Key size 3
    Looking at key  0
    Looking at key  1
    Looking at key  2
    uploaded (3) out of (3)
    ready to deploy!
    ```

- 更新糖果机配置
`ts-node ../metaplex/js/packages/cli/src/candy-machine-v2-cli.ts update_candy_machine -e devnet -k ~/.config/solana/devnet.json -cp config.json`

## 更改NFT的说明

假设您不喜欢用于测试的 NFT 集合，并且有了更好的想法。你需要在这里小心！每当您更改您的集合时，您都需要按照与之前相同的步骤来部署 NFT。
删除.cacheMetaplex CLI 的糖果机命令生成的文件夹。
将您的 NFT 文件更改为您想要的任何文件！
通过 CLI运行 Metaplex 的upload命令以上传 NFT 并创建新的糖果机。
通过 CLI运行 Metaplex 的verify命令，以确保 NFT 已上传并且糖果机已正确配置。
.env使用新地址更新您的文件。
如果你搞砸了这些步骤中的任何一个，一切都会崩溃。所以小心。
