# substrate-runtime-developer

https://github.com/substrate-developer-hub/substrate-pallet-template

https://docs.patract.io/en/

https://www.shawntabrizi.com/substrate-js-utilities/codec/

https://szulborski.eu/wymiana-kluczy-ssh-na-ed25519/

Book: https://w3f.github.io/parachain-implementers-guide/whence-parachains.html

Auction: https://medium.com/polkadot-ecosystem-promoteam/what-is-polkadot-parachain-auction-and-how-it-will-reveal-the-hidden-power-of-the-polkadot-f4fc5edc3d20 

https://w3f.github.io/parachain-implementers-guide/protocol-overview.html

https://github.com/substrate-developer-hub/awesome-substrate

https://github.com/open-web3-stack/open-runtime-module-library

!! https://decoded.polkadot.network/2021submission

https://en.wikipedia.org/wiki/Diffie%E2%80%93Hellman_key_exchange

---

```
Parachain's logic is encoded by wasm blob. Compiling and executing it can be time consuming. There is an interest in sandboxing the execution pipeline. Specifically, in the number of physical memory consumed. There is RLIMIT_RSS but that was retired long time ago. A mechanism like cgroups can help with this. cgroups can be v1 and v2. We would like to know, should we focus on one of those or do we need both. v2 adoption speed in general is quite slow.
That's not the primary reason why I am asking though. The question of what kernel versions are in the wild is already popped up a few times before. This is because it is generally useful to know what kind of Linux features we can or cannot target.

https://man7.org/linux/man-pages/man2/userfaultfd.2.html
https://www.redhat.com/sysadmin/cgroups-part-one
```


---

https://doc.rust-lang.org/stable/rust-by-example/

https://github.com/rust-lang/rustlings

https://github.com/SubstrateDevAcademy

https://rust-analyzer.github.io/ (The Matklad)

https://github.com/SubstrateCourse/

https://substrate.dev/recipes/runtime-printing.html#printing-from-the-runtime

https://github.com/dtolnay/cargo-expand

# VSCode plugins

1. https://marketplace.visualstudio.com/items?itemName=vadimcn.vscode-lldb

2. https://github.com/rust-analyzer/rust-analyzer

3. https://github.com/paritytech/vscode-substrate
