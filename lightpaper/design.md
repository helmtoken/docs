# Design

### Architecture

![](<.gitbook/assets/Untitled Diagram.drawio (2).png>)

code - EVM code

![](<.gitbook/assets/Untitled Diagram.drawio (1).png>)

virtual machine - Ethereum Virtual Machine (EVM)

![](<.gitbook/assets/Untitled Diagram.drawio.png>)

runtime system (process) - Ethereum node (Geth, Parity, etc.)

### User flow

```mermaid
sequenceDiagram
    User->>Helm: Locks up XEN for 6 years
    Helm->>User: Mints HLM
    User->>Helm: Stakes HLM
    Helm->>Staking: Started stake
    alt
        User->>Helm: Request to end stake early
        Helm->>Staking: Ended stake with penalty
    else
        User->>Helm: Request to end stake on time
        Helm->>Staking: Ended stake
    else
        User->>Helm: Request to end stake late
        Helm->>Staking: Ended stake with penalty
    else
        User->>Helm: Request to defer stake
        Helm->>Staking: Deferred stake
    end
    Helm->>User: Mints HLM
```

### Contract flow

```mermaid
sequenceDiagram
    Deployer->>EVM: Trigger Helm contract deployment
    EVM->>Helm contract: Create Helm contract
    Helm contract->>EVM: Trigger ERC20 contract deployment
    EVM->>ERC20 contract: Create ERC20 contract
```
