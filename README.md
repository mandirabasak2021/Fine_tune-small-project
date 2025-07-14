[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/mandirabasak2021/Fine_tune-small-project/blob/main/gamedialogue.ipynb)

# Game Dialogue Generator using DistilGPT2

This project fine-tunes a lightweight GPT2-based model (`DistilGPT2`) to generate dynamic, game-relevant text such as NPC dialogue, quest descriptions, or game item lore, using the [Viggo Dataset](https://nlds.soe.ucsc.edu/viggo).

---

## Project Overview

This project was developed as an alternative to 3D model generation. It demonstrates how a small language model can be adapted to generate natural and engaging in-game dialogue using a fine-tuned transformer model and exposed via an API or interface.

---

## What It Does

-  Loads and processes a game dialogue dataset (Viggo)
-  Fine-tunes `DistilGPT2` on game-relevant text (`target` column)
-  Generates text like:
  - _"Tell me about Far Cry 3"_
  - _"What kind of game is Tomb Raider?"_
-  Deploys as:
  - FastAPI/Flask API (`/generate?prompt=...`)
  - Optional: Gradio interface

---

##  Dataset

- **Viggo Dataset**: contains annotated video game conversations
- Trained on 1–20% challenge splits
- Texts extracted from the `target` column

---

##  How to Run

###  In Google Colab

1. Open the Colab notebook [here](#).
2. Upload dataset files (CSV)
3. Run all cells to:
   - Load + clean dataset
   - Tokenize using Hugging Face Tokenizers
   - Fine-tune `DistilGPT2`
   - Save model
   - Generate sample outputs

###  Locally (optional API)

```bash
# Clone this repo
git clone https://github.com/yourusername/game-dialogue-generator.git
cd game-dialogue-generator

# Install dependencies
pip install -r requirements.txt

# Start FastAPI or Flask server
python app.py

###  Sample Output
**Prompt:** Tell me about Far Cry 3  
**Generated:** Far Cry 3 is an action-adventure game set on a tropical island. It features first-person gameplay and was released in 2012.
