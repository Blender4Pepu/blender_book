# Contract Details

### Constants

```
uint256 public constant FEE_AMOUNT = 1000 * 10 ** 18;
```
- **FEE_AMOUNT**: Fixed fee for each deposit in **BLENDER** tokens (1000 BLENDER).

### State Variables

```
IERC20 public immutable blenderToken;
```
- **blenderToken**: ERC-20 token used for transaction fees.

```
mapping(bytes32 => Deposit) public deposits;
```
- **deposits**: Maps the hashed secret to a **Deposit** structure.

### Deposit Structure

```
struct Deposit {
    uint256 amount;
    bytes32 hashedSecret;
    uint256 createdAt;
    bool spent;
}
```
- **amount**: Amount of PEPU deposited.
- **hashedSecret**: Hash of the secret used for withdrawal.
- **createdAt**: Timestamp of the deposit.
- **spent**: Status indicating whether the deposit has been withdrawn or refunded.
