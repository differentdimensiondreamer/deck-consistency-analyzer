# deck-consistency-analyzer
Python-based probability simulator for Yu-Gi-Oh! decks. Test opening hands, evaluate combo consistency, and analyze engine vs. non-engine ratios with a set number of randomized draws. Built on hypergeometric probability principles and implemented using Monte Carlo simulation for realistic results.

# Yu-Gi-Oh! Deck Consistency Analyzer

This Python script simulates opening hands in a Yu-Gi-Oh! deck and calculates the probability of drawing into desired combos. It is build on hypergeometric probability principles and implemented using Monte Carlo simulation for realistic results. It’s designed for a **data-driven deckbuilding approach**, so you can move beyond gut feelings and measure your deck’s actual consistency.  

---

## Features
- Input your decklist (card names + quantities).  
- Define success conditions (e.g., “at least 1 starter,” “no more than 1 brick,” etc.).  
- Built-in support for draw cards like **Pot of Desires, Pot of Prosperity, Extravagance, Upstart Goblin, and Duality**.  
- Runs a set number of simulated hands to estimate:  
  - Probability of success  
  - Standard error  
  - 95% Wilson confidence interval  
  - Probability of opening at least 1, 2, or 3 non-engine cards  

---

## How to Get Started
1. Clone this repository:  
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   cd <repo-name>
   ```

2. Run the script with Python 3:  
   ```bash
   python deck_simulator.py
   ```

3. Edit the input sections at the top of the script:  

   ```python
   deck_size = 40
   hand_size = 5
   input_cards_here="""
   Cupsie 3
   Cooky 3
   Lollipo 3
   NonEngine 21
   """
   input_possibilities_here="""
   Cupsie
   Cooky
   Lollipo
   """
   num_trials=100000
   ```

   - **input_cards_here** → decklist with `CardName Quantity`  
   - **input_possibilities_here** → success conditions  
   - **num_trials** → number of simulated hands  

---

## Example Output
```
probability of success: 94.46%
standard error (abs): 0.07%
95% CI (Wilson): [94.33%, 94.59%]

Duplicate Non Engine probabilities (opening 5):
Atleast 1 non engine: 94.33% | SE: 0.08% | 95% CI (Wilson): [94.17%, 94.49%]
Atleast 2 non engine: 70.33% | SE: 0.14% | 95% CI (Wilson): [70.05%, 70.61%]
Atleast 3 non engine: 33.34% | SE: 0.15% | 95% CI (Wilson): [33.04%, 33.64%]
```

---

## 🧪 Why Use This?
Yu-Gi-Oh! deckbuilding often relies on vibes and feelings. This simulator turns that into **hard numbers** so you can:  
- Compare builds objectively  
- Test engine vs. non-engine ratios  
- Prepare your deck for specific matchups  

---

## 📜 License
This project is open-source under the MIT license.  
Feel free to fork, modify, and adapt it for your own testing.  
