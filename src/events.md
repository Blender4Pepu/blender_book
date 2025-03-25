# Events

### Deposit Event

```
event Deposited(bytes32 indexed hashedSecret, uint256 amount);
```
- Emitted when a new deposit is made.

### Withdraw Event

```
event Withdrawn(address indexed recipient, uint256 amount);
```
- Emitted when a successful withdrawal is processed.

### Refund Event

```
event Refunded(bytes32 indexed hashedSecret, address to);
```
- Emitted when a refund is issued.