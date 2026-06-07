# ⚡ ZK Treasure Hunt — Marauder's Map

A Zero-Knowledge proof demo game built with **Leo (Aleo)** and vanilla HTML/CSS/JS.

## 🚀 Deployed on Aleo Testnet

| Item | Value |
|------|-------|
| **Program ID** | `treasure_hunt.aleo` |
| **Network** | Aleo Testnet |
| **Deployer** | `aleo192xccjkqdp5c8lwjdp9ldky5egun3jrg4m2fh05r0tldq8cu9qqqv847yj` |
| **Deploy TX** | `at1pedzdd4wcu26grecrujx888qktyvd0450fld0mv9lefwejej2cgqvhm70t` |
| **On-chain Interaction TX** | `at12nhjcehhu9622r28new94e9wdzh3w35yn9agcx870f8gf5s9mc8qjjj4yr` |
| **Explorer** | [View on Testnet Explorer](https://testnet.explorer.provable.com/program/treasure_hunt.aleo) |

## How It Works

1. A treasure is secretly placed on a 5×5 grid
2. You have **5 attempts** to find it by clicking cells
3. Each guess generates a **ZK proof** that verifies hit/miss — without ever revealing where the treasure is hidden
4. The treasure location is only revealed when you win or run out of attempts

## ZK Property

> The proof confirms your guess was checked fairly.  
> The treasure coordinates are **never exposed** — only the boolean result (hit/miss) is public.

---

## Run the Frontend

Just open `index.html` in any browser — no server needed:

```bash
open index.html
# or
python3 -m http.server 8080  # then visit http://localhost:8080
```

---

## Run the Leo Program

### Prerequisites
```bash
curl -L https://install.aleo.org | sh
leo --version
```

### Build & Test
```bash
cd leo/
leo build
```

### Execute transitions locally

**Game master hides treasure at (2, 3) with salt:**
```bash
leo run hide_treasure 2u8 3u8 987654321u64
```

---

## File Structure

```
zk-treasure-hunt/
├── index.html          ← Complete frontend (Harry Potter theme)
├── README.md
└── leo/
    ├── program.json
    └── src/
        └── main.leo    ← Leo ZK program (Leo 4.x syntax)
```

---

## Stack

| Layer    | Tech |
|----------|------|
| ZK Layer | Leo 4.x · Aleo Testnet |
| Frontend | HTML · CSS · Vanilla JS |
| Fonts    | Google Fonts (Cinzel Decorative, Crimson Text) |
| Proof    | Groth16 via Aleo VM |
