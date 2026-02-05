# apo-cli 💊

CLI for [apohealth.de](https://www.apohealth.de) – search pharmacy products, manage your cart, checkout in browser.

## Installation

```bash
uv tool install git+https://github.com/Lars147/apo-cli
```

No dependencies – pure Python stdlib.

## Usage

```bash
# Search products
apo search "Aspirin"
apo search "Ibuprofen 400"

# Product details
apo product aspirin-complex-granulat-20-st-beutel-4114918

# Browse categories
apo categories
apo list --category bestseller --limit 10

# Cart management
apo cart                           # Show cart
apo cart add <variant_id>          # Add product
apo cart add <variant_id> --qty 2  # Add with quantity
apo cart remove <variant_id>       # Remove product
apo cart clear                     # Clear cart

# Checkout (opens browser)
apo cart checkout
```

## Workflow

1. `apo search "Aspirin"` → Find product
2. `apo product <handle>` → Get variant ID
3. `apo cart add <variant_id>` → Add to cart
4. `apo cart checkout` → Pay in browser

## For AI Agents

This CLI is designed for AI assistants:
- Structured output, no interactive prompts
- Session persistence across conversations
- Clear commands for automation

MCP server planned for native Claude integration.

## License

MIT
