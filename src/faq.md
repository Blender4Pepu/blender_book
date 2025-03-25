# Frequently Asked Questions

### General Questions
**Q: What is the Blender CLI tool?**  
A: It's a command-line interface for interacting with the Blender smart contract on Pepe Unchained blockchain, enabling secure PEPU token deposits and withdrawals.

**Q: Is there a mobile version of the CLI tool?**
A: No, the CLI is designed for desktop environments (Windows/macOS/Linux) only.

**Q: Who maintains this project?**  
A: The GenesisLab Development Team maintains this open-source project with community contributions.

**Q: Does Blender support other blockchains?**
A: Currently, it only operates on the Pepe Unchained blockchain. Cross-chain functionality may be added in future updates.

**Q: What happens if I lose my secret?**  
A: After 30 days, unclaimed deposits can be refunded to the original address using the `refund` function.

**Q: Can I use a hardware wallet?**  
A: Not directly - current implementation requires private key in `.env`. For security, use dedicated wallet with minimal funds.

### Technical Questions
**Q: How are deposits secured?**  
A: Each deposit generates a unique cryptographic secret hash using keccak256, ensuring only the secret holder can withdraw funds.

**Q: Are there deposit limits?**
A: No quantity limits, but amounts must match exact tiers (100/1k/10k/100k/1M PEPU).

**Q: How do I update the CLI?**
A: Run `git pull` in the installation directory, then `pnpm install` to update dependencies.

**Q: Where are wallet credentials stored?**  
A: Private keys are **never stored** - only read from `.env` file at runtime. The CLI has no internal storage mechanism.

**Q: Why display balances before/after transactions?**  
A: The `displayBalances()` function shows real-time PEPU/BLENDER changes, helping verify successful operations.

**Q: How are secrets generated?**  
A: Using `ethers.utils.randomBytes(32)` for cryptographically secure randomness, then hashed with keccak256 per contract requirements.

**Q: How to change recipient address?**  
A: Update `RECIPIENT_ADDRESS` in `.env` - withdrawals always send to this address through `withdraw()` function parameter.

### Troubleshooting
**Q: Why is my transaction failing?**  
Common issues:
- Insufficient BLENDER tokens for fees (requires 1000 BLENDER)
- Invalid deposit amount (must be 100/1k/10k/100k/1M PEPU)
- Incorrect RPC endpoint in `.env`

**Q: Where are my secrets stored?**  
A: Secrets are saved locally in `secrets.json` - back up this file securely.

**Q: What happens if .env is missing values?**  
A: CLI crashes immediately with "Cannot read properties of undefined" - always verify all `.env` variables are set before launching.

### Project Support
**Q: How can I contribute?**  
A: Submit pull requests or report issues on our [GitHub repository](https://github.com/Blender4Pepu/blender_cli).

**Q: Where can I get help?**  
A: For technical support, email *blender4pepu@proton.me* with detailed error logs.
