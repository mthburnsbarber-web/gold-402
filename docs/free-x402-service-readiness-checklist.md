# Free x402 Service Readiness Checklist

Use this before submitting a payable API, MCP server, facilitator, framework, or
tool to an x402 directory.

## The front door

- A machine can find the payable endpoint without reading a marketing page.
- The endpoint returns HTTP `402 Payment Required` before payment.
- The payment challenge includes amount, asset, network, payee, and replay
  instructions expected by the protocol you implement.
- If the endpoint requires parameters before it can quote a price, publish one
  minimal request body.
- A free docs URL explains the request shape and the paid response shape.

## The purchase

- Price is stated in the smallest useful unit or as an exact decimal.
- Network and token are explicit.
- Overpayment, underpayment, duplicate payment, and expired challenge behavior
  are documented.
- Failed upstream work does not silently settle as a successful paid response.
- A caller gets a stable receipt or payment response header.

## The listing

- One service per listing.
- One factual sentence.
- Direct URL to the endpoint, manifest, docs, or repo.
- No "best", "revolutionary", "seamless", or unsupported performance claims.
- Include an example request in the PR body when `{}` is not enough.

## Minimal PR body

```text
Name:
URL:
Category:
Description:
Endpoint returns 402 without payment: yes/no
Example: {"input":"minimal request"}
Notes:
```
