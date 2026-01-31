# 🃏 Pai Tee Taek (ตีแตก): Strategy & Rules

This document outlines the specific rules, ranking systems, and strategic filters for **Pai Tee Taek**, designed for Monte Carlo simulation and risk analysis.

---

## 📋 Game Overview
* **Dealing:** Each player is dealt **4 cards**.
* **The Decider:** The dealer flips **1 center card** from the remaining deck.
* **Objective:** To win, a player must have at least one card in their hand that matches the **same suit** as the center card and holds a **higher rank**.

---

## ⚔️ Winning Conditions
Victory is determined by a two-tier verification:

1.  **Tier 1 (Suit Match):** You must hold a card of the same suit as the center card.
2.  **Tier 2 (Rank Match):** That matching card must have a higher rank than the center card.

> **Note:** If you have no matching suit, or the suit matches but the rank is lower, you lose the bet.

---

## 🔢 Special Ranking (The "2 Kills A" Rule)
This version of the game uses a non-standard hierarchy to allow for "trap" cards:

| Rank Priority | Card(s) | Result vs. Center Card |
| :--- | :--- | :--- |
| **Highest** | **A (Ace)** | Beats K, Q, J... down to 3. **Loses to 2.** |
| **The Counter** | **2** | **Beats A only.** Loses to every other number (3, 4, 5...). |
| **Standard** | **K, Q, J, 10 - 3** | Follows standard descending numerical order. |
| **Lowest** | **3** | The weakest card in this specific hierarchy. |

---

## 🌑 The Dark Rules (Risk Management)

### 1. The Discard (Fold)
* Players may look at their 4 cards and choose to "Fold" before the center card is revealed.
* **Penalty:** Pay a small predetermined fee instead of the full bet.

### 2. Blind Play (Dark Play)
* Players choose to bet **without looking** at their own cards.
* **Win:** Receive **100%** of the potential payout.
* **Loss:** Pay only **50%** of the bet amount.
* **Math Logic:** This strategy exploits the Expected Value ($EV$) where the loss is capped at $0.5x$ while the win remains $1.0x$.

---

## 💡 Play Criteria: "The 10+ Filter"
When playing "Light" (looking at cards), the player only commits to the bet if the following conditions are met:

1.  **Diversity:** The hand must contain at least **3 different suits**.
2.  **Quality:** Each of those unique suits must be represented by a card with a rank of **10 or higher**. (In this filter, 2 is treated as the lowest value).
3.  **Betting:** A flat bet of **500 units** is placed consistently when these conditions are met. Otherwise, the player folds.

---

## 🎯 Simulation Goals (Monte Carlo)

### Goal 1: Performance Comparison
Run a **100,000-round simulation** to compare:
* **Blind 100%:** Never looking at cards to capitalize on the 50% loss rule.
* **Strategic Look:** Using the "10+ Filter" and folding all other hands.
* **Result:** Determine which strategy yields the highest cumulative net profit.

### Goal 2: Optimization
Identify the optimal "Look" strategy by testing variations:
* Does lowering the rank threshold to 8+ or 9+ improve the total profit by increasing play frequency?
* What is the "sweet spot" between win rate and the number of games played?

---

### File Structure

- TeeTaek_ver1 : no Central Pot and 1 player
- TeeTaek_ver2 : have Central Pot and 6 players