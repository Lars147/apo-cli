# apo-cli 💊

CLI für [apohealth.de](https://www.apohealth.de) – Apotheken-Produkte suchen, Warenkorb verwalten, im Browser bestellen.

## Features

- 🔍 **Produktsuche** – Nach Name oder PZN suchen
- 📦 **Produktdetails** – Preise, Verfügbarkeit, Beschreibung
- 🗂️ **Kategorien** – Collections durchstöbern
- 🛒 **Warenkorb** – Hinzufügen, entfernen, anzeigen
- 🌐 **Checkout** – Öffnet Browser mit befülltem Warenkorb

## Installation

```bash
# Mit uvx (empfohlen) - einmalig ausführen
uvx --from git+https://github.com/Lars147/apo-cli apo --help

# Mit pipx
pipx install git+https://github.com/Lars147/apo-cli

# Oder direkt ausführen
python3 apo_cli.py --help
```

**Keine Dependencies!** Pure Python stdlib.

## Verwendung

```bash
# Produktsuche
apo search "Aspirin"
apo search "Ibuprofen 400"

# Produktdetails
apo product aspirin-complex-granulat-20-st-beutel-4114918

# Kategorien anzeigen
apo categories

# Produkte einer Kategorie
apo list --category bestseller --limit 10

# Warenkorb
apo cart                          # Anzeigen
apo cart add 32907653677119       # Hinzufügen (Variant-ID)
apo cart add 32907653677119 --qty 2
apo cart remove 32907653677119    # Entfernen
apo cart clear                    # Leeren

# Checkout im Browser
apo cart checkout

# Status
apo status
```

## Workflow

1. `apo search "Aspirin"` – Produkt finden
2. `apo product <handle>` – Details & Variant-ID holen
3. `apo cart add <variant_id>` – In Warenkorb legen
4. `apo cart checkout` – Im Browser bezahlen

## Technische Details

- **API**: Shopify Storefront APIs (undokumentiert, aber stabil)
- **Session**: Cookies werden in `apo_cookies.json` gespeichert
- **Warenkorb**: Cart-Token in `apo_cart.json` für Persistenz

## Limitierungen

- Kein Login (OAuth + Captcha zu komplex)
- Checkout nur im Browser (Zahlungsabwicklung)
- PZN-Direktsuche eingeschränkt (Volltext-Suche funktioniert)

## Für AI-Agenten

Diese CLI ist optimiert für AI-Assistenten:
- Strukturierte JSON-Ausgabe möglich
- Klare Befehle ohne interaktive Prompts
- Session-Persistenz über Gespräche hinweg

Geplant: MCP Server für native Claude-Integration.

## Lizenz

MIT
