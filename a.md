## The problem Superloud solves
Superloud helps connecting musicians and fans through a fun web3 karaoke platform.

On Superloud, artists can upload the lyrics video of their songs to our catalog, allowing fans to easily create and share their own karaoke videos as well as discover new artists.

Artists can also create song challenges and set bounties for the best covers of their songs, giving fans the opportunity to showcase their talents and earn rewards. Additionally, voters selected by the contestants will be able to vote for the best cover, connecting the artist’s fanbase to contestants’ communities, with voters themselves earning a share of the reward as well. The challenge creator can also create "charity" challenge (paid participation + vote, with all funds sent to a whitelisted charity picked by the winner)

## **Why Superloud ? **

making a living as an artist is difficult, gaining visibility is difficult
making a living as a cover artist is even more impossible
karaoke is fun!
specific music genre might not be the cup of tea of a lot of people. A way to bring visibility and a income stream to artists could be to create “Pop cover” or “cover in the style of…”. This is also a great way to discoverdifferent music genre and/or artists that you would never listen to !
TV sucks for cover contests, but they have a good idea for one thing: funny compilation, which can be a way for some people to gain visibility !
You don’t necessarily want your artist account to be linked to your hard earnt funds - a way to be a bit more safe is to decide where your funds will be sent
Superloud also aims to bring Web2 user experience closer to Web3 to reduce certain blocking points (getting a wallet, getting gas token...)

## Challenges I ran into
I was supposed to use a Chainlink adapter to verify wheter or not a curator is the creator of the song, but ended up spending several days trying to get a local node to run. I ended up leaving the bounty, but I have the adapter !

This was the first time I wrote Solidity and created a subgraph ; I'm more used to front-end and app architecture, so it was a
bit of a challenge

My idea was definitely too big for the hackathon ! My teammate ended up not having the time to participate - he usually works on smart contracts/subgraphs/more backend things and I handle front-end/project design & architecture. I left out the challenge part, sybil resistance and notification part to focus on the karaoke experience.

## Monorepo structure

- `apps/webapp` - Superloud front-end (webapp - SolidStart, wagmi)
- `apps/smartcontracts-solidity/*` - Superloud solidity smart contracts (Catalog & Challenges)
- `apps/smartcontracts-warp/*` - Superloud Warp (Smartweave) smart contracts (Voting)
- `apps/subgraph-catalog` - Subgraph for the karaoke catalog ([hosted service](https://thegraph.com/hosted-service/subgraph/naomihauret/superloud-catalog-mumbai))
- `apps/subgraph-challenges` - Subgraph for the karaoke challenges

## Tech stack overview

- NFT Music, Artists & Playlist API: [Spinamp](https://dev.spinamp.xyz/)
- Song catalog & challenge smart contracts: Solidity
- Challenge entrance ticket & karaoke trial ticket: Unlock Protocol
- Voting smart contract: Smartweave
- Oracle: Chainlink
- Vote sybil resistance: Polygon ID
- Automated rewards distribution: Superfluid
- Cross-chain distribution: Connextq
- Subgraph:
- Social login: Arcana
- Storage: IPFS (infura-ipfs, w3ui)
- Video NFT & CDN: Livepeer
