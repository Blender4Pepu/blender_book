# Functions

### Constructor

```
constructor(address _blenderToken, address _initialOwner) Ownable(_initialOwner)
```
- **_blenderToken**: Address of the **BLENDER** token contract.
- **_initialOwner**: Address of the contract owner.

Initializes the contract with the **BLENDER** token address and the owner address.

### `deposit(bytes32 hashedSecret)`

```
function deposit(bytes32 hashedSecret) external payable
```
- **hashedSecret**: Keccak256 hash of the secret required for withdrawal.

#### Requirements:
- Deposit amount must be one of the fixed options (100, 1000, 10000, 100000, or 1000000 ETH).
- User must pay **1000 BLENDER** tokens as a fee.
- The hashed secret must be unique (not previously used).

Emits:
- `Deposited` event on successful deposit.

### `withdraw(bytes calldata secret, address payable recipient)`

```
function withdraw(bytes calldata secret, address payable recipient) external
```
- **secret**: Original secret used to generate the deposit hash.
- **recipient**: Address where the ETH will be sent.

#### Requirements:
- The provided secret must match the stored **hashedSecret**.
- Deposit must not be already spent.
- The recipient address must be valid.

Emits:
- `Withdrawn` event on successful withdrawal.

### `refund(bytes32 hashedSecret)`

```
function refund(bytes32 hashedSecret) external
```
- **hashedSecret**: Hash of the secret associated with the deposit.

#### Requirements:
- Refund is only available after **30 days** from the deposit time.
- The deposit must not be already spent.

Emits:
- `Refunded` event on successful refund.