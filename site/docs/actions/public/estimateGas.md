# estimateGas

Estimates the gas necessary to complete a transaction without submitting it to the network.

## Import

```ts
import { estimateGas } from 'viem'
```

## Usage

```ts
import { estimateGas } from 'viem'
import { publicClient } from '.'
 
const gasEstimate = await estimateGas(publicClient, { // [!code focus:7]
  request: {
    from: '0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266',
    to: '0x70997970c51812dc3a010c7d01b50e0d17dc79c8',
    value: parseEther('1')
  }
})
```

## Returns

`bigint`

The gas estimate (in wei).

## Configuration

### request.data (optional)

- **Type:** `0x${string}`

Contract code or a hashed method call with encoded args.

```ts
const gasEstimate = await estimateGas(publicClient, {
  request: {
    data: '0x...', // [!code focus]
    from: '0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266',
    to: '0x70997970c51812dc3a010c7d01b50e0d17dc79c8',
    value: parseEther('1')
  }
})
```

### request.from (optional)

- **Type:** `Address`

Transaction sender.

```ts
const gasEstimate = await estimateGas(publicClient, {
  request: {
    from: '0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266', // [!code focus]
    to: '0x70997970c51812dc3a010c7d01b50e0d17dc79c8',
    value: parseEther('1')
  }
})
```

### request.gasPrice (optional)

- **Type:** `bigint`

The price (in wei) to pay per gas. Only applies to [Legacy Transactions](/TODO).

```ts
const gasEstimate = await estimateGas(publicClient, {
  request: {
    from: '0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266',
    gasPrice: parseGwei('20'), // [!code focus]
    to: '0x70997970c51812dc3a010c7d01b50e0d17dc79c8',
    value: parseEther('1') 
  }
})
```

### request.maxFeePerGas (optional)

- **Type:** `bigint`

Total fee per gas (in wei), inclusive of `maxPriorityFeePerGas`. Only applies to [EIP-1559 Transactions](/TODO)

```ts
const gasEstimate = await estimateGas(publicClient, {
  request: {
    from: '0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266',
    maxFeePerGas: parseGwei('20'),  // [!code focus]
    to: '0x70997970c51812dc3a010c7d01b50e0d17dc79c8',
    value: parseEther('1')
  }
})
```

### request.maxPriorityFeePerGas (optional)

- **Type:** `bigint`

Max priority fee per gas (in wei). Only applies to [EIP-1559 Transactions](/TODO)

```ts
const gasEstimate = await estimateGas(publicClient, {
  request: {
    from: '0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266',
    maxFeePerGas: parseGwei('20'),
    maxPriorityFeePerGas: parseGwei('2'), // [!code focus]
    to: '0x70997970c51812dc3a010c7d01b50e0d17dc79c8',
    value: parseEther('1')
  }
})
```

### request.to (optional)

- **Type:** `Address`

Transaction recipient.

```ts
const gasEstimate = await estimateGas(publicClient, {
  request: {
    from: '0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266',
    to: '0x70997970c51812dc3a010c7d01b50e0d17dc79c8', // [!code focus]
    value: parseEther('1')
  }
})
```

### request.value (optional)

- **Type:** `bigint`

Value (in wei) sent with this transaction.

```ts
const gasEstimate = await estimateGas(publicClient, {
  request: {
    from: '0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266',
    to: '0x70997970c51812dc3a010c7d01b50e0d17dc79c8',
    value: parseEther('1') // [!code focus]
  }
})
```

### blockNumber (optional)

- **Type:** `number`

The block number to perform the gas estimate against.

```ts
const gasEstimate = await estimateGas(publicClient, {
  blockNumber: 15121123n, // [!code focus]
  request: {
    from: '0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266',
    to: '0x70997970c51812dc3a010c7d01b50e0d17dc79c8',
    value: parseEther('1') 
  }
})
```

### blockTag (optional)

- **Type:** `'latest' | 'earliest' | 'pending' | 'safe' | 'finalized'`
- **Default:** `'latest'`

The block tag to perform the gas estimate against.

```ts
const gasEstimate = await estimateGas(publicClient, {
  blockTag: 'safe', // [!code focus]
  request: {
    from: '0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266',
    to: '0x70997970c51812dc3a010c7d01b50e0d17dc79c8',
    value: parseEther('1') 
  }
})
```

## Example

TODO