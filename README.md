# Small Worlds 🌍🧬
### Exploring how a few connections can make a network surprisingly small

An interactive simulation inspired by **Six Degrees of Separation** and the **Watts–Strogatz small-world model**.

Instead of simply asking whether two people can be connected through a short chain, this project explores **why large networks can remain surprisingly well connected when only a small number of long-range connections are introduced**.

The simulation uses a biological-looking network to make this phenomenon intuitive and visual.

---

## The Question

> **How can a network that is mostly locally connected become surprisingly small when only a few long-range connections are introduced?**

Six Degrees of Separation is the starting point for this project.

The goal is not to prove that everything in nature has "six degrees." Instead, the project investigates the underlying **small-world phenomenon** and how it emerges from network structure.

---

## Background

- **Six Degrees of Separation** popularized the idea that seemingly distant people can be connected through surprisingly short chains.
- **Watts & Strogatz (1998)** showed that a network can develop short paths while retaining strong local clustering when a small amount of long-range rewiring is introduced.
- This demonstrated that the small-world phenomenon can emerge from **network structure**, rather than being something unique to human social networks.
- Similar network concepts can be used to study many complex systems, including biological networks.

This project takes that idea as a starting point and turns it into an interactive experiment.

---

## What It Does

### 1. Generates a simple network

The simulation starts with a small, mostly locally connected network.

Nodes are given simple biological roles:

- 🌱 Producer
- 🐛 Herbivore
- 🦅 Carnivore
- 🍄 Decomposer

These roles provide an intuitive visual context.

> **Important:** The current simulation is a structural network simulation, not a complete biological food-web model. The biological roles are used to make the network easier to understand visually.

### 2. Lets the user explore connections

The user can select two nodes and see the path between them.

For example:

```text
A → B → C → D
```

The simulation shows how many steps separate the two nodes.

### 3. Adds long-range connections

The user can introduce connections between distant parts of the network.

For example:

```text
A — B — C — D — E — F
╰─────────────────────╯
```

The new connection acts as a shortcut.

### 4. Measures the effect

The simulator calculates properties of the actual network:

- Average shortest-path length
- Clustering coefficient
- Number of connected components
- Average degree

### 5. Shows the network changing

As long-range connections are introduced, the network can move through three broad structural states:

```text
Ordered network
      ↓
A few long-range shortcuts
      ↓
Small-world region
      ↓
Increasingly random network
```

The important observation is that **path length can decrease significantly while clustering remains relatively high**.

### 6. Runs the main experiment

The simulator can sweep through different rewiring probabilities and plot:

- `L(p) / L(0)` — normalized average path length
- `C(p) / C(0)` — normalized clustering coefficient

This allows the small-world region to be observed as an experimental result rather than simply stated as a conclusion.

---

## Why This Matters

Most Six Degrees projects stop at:

> **"Find a short path between two people."**

This project uses Six Degrees only as the **starting point**.

The deeper question is:

> **What makes a large network surprisingly well connected?**

By allowing users to introduce a small number of long-range connections and observe how the network changes, the simulation makes the underlying mechanism visible.

The project therefore combines:

- Intuition
- Experimentation
- Graph theory
- Network visualization

rather than simply recreating the Six Degrees game.

---

## Interactive Experience

The simulation is designed to be understood visually before introducing the mathematics.

The intended experience is:

```text
Explore the network
        ↓
Choose two nodes
        ↓
See their path
        ↓
Add a long-range connection
        ↓
Watch the distance change
        ↓
Repeat
        ↓
Observe the small-world effect
        ↓
Explore the mathematics
```

Technical concepts such as BFS, clustering coefficient, and rewiring probability are introduced after the visual experiment rather than overwhelming the user at the beginning.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML, CSS, JavaScript |
| Visualization | Canvas / D3.js |
| Graph representation | JavaScript adjacency sets |
| Shortest paths | Breadth-First Search (BFS) |
| Network metrics | Custom calculations |
| Simulation | Watts–Strogatz-style rewiring |
| Version control | Git / GitHub |

A Python/NetworkX backend may be added later if larger networks require heavier computation.

---

## Algorithm Notes

### Shortest Path

**Breadth-First Search (BFS)** is used to find the shortest path between nodes in the unweighted network.

### Clustering Coefficient

The clustering coefficient measures how strongly a node's neighbors are connected to one another.

The overall clustering coefficient is calculated from the local clustering values of the nodes.

### Rewiring

The simulation starts with an ordered network.

Edges are progressively rewired with probability `p` to introduce long-range connections while avoiding self-loops and duplicate edges.

---

## Roadmap

- [ ] **v1** — Simple interactive network and path exploration
- [ ] **v1.1** — Long-range connection interaction
- [ ] **v1.2** — Live path-length and clustering measurements
- [ ] **v1.3** — Main Watts–Strogatz experiment and graph
- [ ] **v2** — Introduce real documented biological interaction data
- [ ] **v3** — Compare different network types using the same measurements

A possible future data source is **Global Biotic Interactions (GloBI)**, which provides documented biological interactions.

---

## Running Locally

```bash
git clone https://github.com/Advaitha07/SmallWorlds.git
cd SmallWorlds
```

For a simple HTML/CSS/JavaScript implementation, the project can be opened directly in a browser.

If a build system is introduced later:

```bash
npm install
npm run dev
```

---

## What This Demonstrates

- Graph representation
- Breadth-First Search
- Shortest-path analysis
- Clustering coefficient calculation
- Network simulation
- Probability and random rewiring
- Interactive data visualization
- Experimental design
- Translating an abstract mathematical concept into an intuitive visual experience

Most importantly, the project demonstrates a simple phenomenon:

> **A network does not need to become completely random to become surprisingly well connected.**

---

## References

- Watts, D. J., & Strogatz, S. H. (1998). *Collective dynamics of 'small-world' networks*. **Nature, 393**, 440–442.
- Milgram, S. (1967). *The Small World Problem*. **Psychology Today, 2**, 60–67.
- Global Biotic Interactions (GloBI).

---

## License

MIT
