## Next app with uniswap

To start the demo:

```bash
yarn        # install dependencies
yarn dev    # run the development server
# or
npm i       # install dependencies
npm run dev # run the development server
```

Navigate to [http://localhost:3000](http://localhost:3000) to see the widget.

---

The `SwapWidget` component is passed everything it needs to render:

- `jsonRpcEndpoint`: a JSON-RPC endpoint; in this case "https://goerli.infura.io/v3/{INFURA_KEY}"
- `tokenList`: a TokenList; in this case "https://gateway.ipfs.io/ipns/tokens.uniswap.org"
- `provider`: an EIP1193 Provider; in this case from `connectors.ts`

In addition, it is passed these optional props to flesh out the demo:

- `locale`: the locale in which to render, in this case "en-US"
- `onConnectWallet`: a callback to invoke when a user clicks "Connect your wallet"
- `defaultInputTokenAddress`: the default input token address, or "NATIVE" for Ether
- `defaultInputAmount`: the default input token amount
- `defaultOutputTokenAddress`: the default output token amount, in this case the address of the Uniswap (UNI) token

For all available props (including theming), refer to the documentation at https://docs.uniswap.org/sdk/widgets/swap-widget.

### Passing a provider

This project uses [@web3-react](https://github.com/NoahZinsmeister/web3-react) to connect to an Ethereum Provider. The demo uses MetaMask. See `components/Web3Connectors.tsx`.

### Localization

The `SwapWidget` component will render in whichever supported locale is passed to the `locale` prop. The demo uses en-US, but includes a selector to demonstrate additional locales.
