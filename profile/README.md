
<div align="center">
  <table>
    <tr align="left">
      <td>
        <h1>Othentic</h1>
      </td>
      <td>
        <h4>AVS Development Framework</h4>
        <div>
          <a href="https://docs.othentic.xyz/main"><b>Documentation</b></a> •
          <a href="https://github.com/Othentic-Labs/avs-examples"><b>Examples</b></a>
        </div>
      </td>
    </tr>
  </table>
</div>

## AVS Structure on Othentic Stack

The Othentic Stack enables developers to build an AVS by abstracting away common technical challenges and low-level infrastructure details. Developers focus solely on implementing the two key business actors of AVSs, "Performer" and "Attester" (collectively forming the validator), while their respective business logic is handled by off-chain services 
- [Execution Serivce](https://docs.othentic.xyz/main/avs-framework/othentic-consensus/execution-service) 
- [Validation Service](https://docs.othentic.xyz/main/avs-framework/othentic-consensus/validation-service)

### Layer1 Components

| Contract | Description |
|----------|-------------|
| [Othentic Registry](https://docs.othentic.xyz/main/avs-framework/smart-contracts/othentic-registry) | Singleton contract facilitating the integration with shared security protocols and AVSs.  |
| [AVS Governance](https://docs.othentic.xyz/main/avs-framework/smart-contracts/avs-governance) | Governance contract to manage AVS rules |
| [L1 Message Handler](https://docs.othentic.xyz/main/avs-framework/smart-contracts/message-handlers#l1-message-handler) | Facilitates L1 → L2 messaging |

---

### Layer2 Components

| Contract | Description |
|----------|-------------|
| [Attestation Center](https://docs.othentic.xyz/main/avs-framework/smart-contracts/attestation-layer) | Core AVS contract to verify task proofs and track execution |
| [OBLS](https://docs.othentic.xyz/main/avs-framework/smart-contracts/othentic-bls-obls) | Performs BLS signature verification for AVS task validation |
| `BN256G2` | Cryptographic logical contract used by OBLS |
| [L2 Message Handler](https://docs.othentic.xyz/main/avs-framework/smart-contracts/message-handlers#l2-message-handler) | Facilitates L2 → L1 messaging |


## Install Othentic CLI

Install using npm:
```
npm i -g @othentic/othentic-cli
```

## Protocols/ Libraries Used
- [LayerZero](https://layerzero.network/)
- [libp2p](https://github.com/libp2p/js-libp2p)

## Quickstart Examples 
Check out our ready-to-use AVS templates and real-world examples here:
- [AVS Examples](https://github.com/Othentic-Labs/avs-examples) 
