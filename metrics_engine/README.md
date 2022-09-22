# LinkPool Metrics Engine

#### Market Metric Notes

```javascript
const URL = "https://api.market.link/v1/metrics/";
const MEATHOD = "POST";
```

```bash
curl --location --request POST 'https://api.market.link/v1/metrics' --header 'Content-Type: text/plain' --data-raw 'SELECT sum(link_reward_sum) as value FROM node_aggregates_by_1d WHERE interval >= now() - interval '\''7 days'\'';'
```

## Links

Golang TAMI Implementation **[https://github.com/linkpoolio/go-tami](https://github.com/linkpoolio/go-tami)**
Original TAMI repo (TypeScript) **[https://github.com/Mimicry-Protocol/TAMI](https://github.com/Mimicry-Protocol/TAMI)**
Market Metrics API Docs **[https://docs.linkpool.io/docs/market_metrics_api_overview](https://docs.linkpool.io/docs/market_metrics_api_overview)**
NFT Metrics TAMI Collection API **[https://rapidapi.com/linkpool-linkpool-default/api/nft-metrics-tami](https://rapidapi.com/linkpool-linkpool-default/api/nft-metrics-tami)**
