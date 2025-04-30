# AI_Assignment_3
# AI Assignment 3: Minimax vs. Alpha‑Beta Pruning on Chess

A comparative study of **Minimax** and **Alpha‑Beta Pruning** search algorithms applied to chess positions, leveraging the Stockfish engine for leaf evaluations. This repo contains Jupyter notebooks that walk through each algorithm’s implementation, visualize principal variation (PV) moves, and report performance metrics (nodes visited, runtime, etc.).

---

## 📂 Repository Structure

```
.
├── .gitmodules             # Git submodule configuration for Stockfish
├── Stockfish/              # Stockfish engine source (official submodule)
├── minimax.ipynb           # Notebook: Minimax implementation & analysis
├── minimax_board.svg       # Example SVG snapshot from Minimax run
├── alpha_beta.ipynb        # Notebook: Alpha‑Beta pruning implementation & analysis
├── alphaBeta_board.svg     # Example SVG snapshot from Alpha‑Beta run
└── README.md               # This file
```

---

## 🛠️ Prerequisites

- **Python 3.8+**
- Clone with submodules:  
  ```bash
  git clone --recursive https://github.com/cs22b053/AI_Assignment_3.git
  ```
- Build Stockfish (in `Stockfish/`):
  ```bash
  cd Stockfish
  make build ARCH=x86-64
  ```
- Python dependencies (from project root):
  ```bash
  pip install -r requirements.txt
  ```
  > **requirements.txt** should include:
  > ```text
  > chess
  > chess-engine
  > cairosvg
  > imageio
  > matplotlib
  > jupyterlab
  > ```

---

## 🚀 Usage

1. **Open and run the notebooks:**
   ```bash
   jupyter lab
   ```
   - `minimax.ipynb`: Explore vanilla Minimax search.  
   - `alpha_beta.ipynb`: Explore Alpha‑Beta pruning.

2. **Reproduce visuals:**  
   Each notebook renders board states via `python-chess` → SVG.  You can export those as `.svg` or generate animated GIFs if extended.

3. **Customize FEN & Depths:**  
   Edit the starting FEN string and search depths in the notebooks to experiment with different positions and complexity.

---

## 📊 Performance Metrics

Both notebooks record and display:

- **Nodes Visited:** Total leaf evaluations at each depth.
- **Time Taken:** Measured wall‑clock runtime for each search.
- **Principal Variation (PV):** Best-move sequence found by each algorithm.

Consider plotting or comparing these metrics side‑by‑side to see how Alpha‑Beta pruning reduces search effort.

---

## 📝 Extending This Assignment

- Integrate a **custom evaluation function** instead of Stockfish’s shallow analysis.
- Increase **search depths** or **piece-square tables** for richer comparison.
- Generate **animated GIFs** of move sequences (see `make_gif` example in supplemental scripts).
- Add **alpha‑beta enhancements** (move ordering, transposition tables).