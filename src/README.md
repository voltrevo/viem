# viem-with-tor-preview

The is a preview of viem with tor integration.

Eg:

```ts
import { createPublicClient, http } from 'viem-with-tor-preview';

async function main() {
  const client = createPublicClient({
    transport: http('https://eth.llamarpc.com/', {
      tor: {
        snowflakeUrl: 'wss://snowflake.pse.dev/',
        filter: () => true,
        onLog: console.log,
      },
    }),
  })

  const blockNumber = await client.getBlockNumber();

  console.log(blockNumber)

  process.exit(0)
}

main()
```

Note: Results can be a bit inconsistent, and it works better in browser than nodejs.
