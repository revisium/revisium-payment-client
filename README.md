# @revisium/payment-client

Generated TypeScript client for the [revisium-payment](https://github.com/revisium/revisium-payment) service.

## Installation

```bash
npm install @revisium/payment-client
```

## Usage

```typescript
import { client, sdk } from '@revisium/payment-client';

client.setConfig({ baseUrl: 'http://localhost:8082' });

const { data } = await sdk.getProviders({ query: { method: 'card' } });
console.log(data?.providers);

const { data: checkout } = await sdk.createCheckout({
  body: {
    organizationId: 'org-1',
    planId: 'pro',
    successUrl: 'https://example.com/success',
    cancelUrl: 'https://example.com/cancel',
  },
});
console.log(checkout?.checkoutUrl);
```

## Regenerating

```bash
npm run generate:download   # fetch latest spec from running service + regenerate
npm run generate             # regenerate from local specs/openapi.json
npm run build                # build dist
```
