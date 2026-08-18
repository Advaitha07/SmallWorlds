# Small Worlds 🌿🕸️

### Can one new connection make a distant route shorter?

**Small Worlds** is an interactive network experiment inspired by **Six Degrees of Separation** and the **Watts–Strogatz small-world phenomenon**.

Instead of starting with people, the project uses a small **illustrative food-web network** so the idea can be seen rather than explained only with mathematics.

> **The goal is not to claim that real ecosystems universally have six degrees or small-world structure. The goal is to make the network mechanism intuitive.**

## 🌱 The idea

Imagine following feeding relationships through a food web:

```text
Grass → Caterpillar → Bird → Fox
```

The path from Grass to Fox is **3 feeding links**.

Now imagine introducing one new, hypothetical feeding interaction between two distant parts of the network. If that new link creates a shorter route, we can see the effect directly.

```text
Before:
Grass → Caterpillar → Bird → Fox
        3 links

After one hypothetical link:
Grass → Caterpillar → Fox
        2 links
```

The important question is:

> **Can one new connection create a shortcut through a network?**

That simple experiment is the starting point for understanding the small-world phenomenon.

## 🔬 What the simulation does

1. **Choose two organisms.**
2. **Trace their existing directed feeding path.**
3. Measure the current shortest path using **Breadth-First Search (BFS)**.
4. Search for a **hypothetical long-range feeding interaction** that is absent from the current web.
5. Only accept the new interaction if it is both topologically distant and **actually makes the selected route shorter**.
6. Compare the route before and after.
7. If no valid shortcut exists, the simulation explicitly says so instead of inventing a connection.

This last case matters. **No useful connection is itself a result.**

## 🐛 About the food web

The organisms and interactions are deliberately small and illustrative. They are used to make graph structure understandable and are **not presented as a complete real-world ecosystem**.

Each directed arrow represents:

```text
food / resource → consumer
```

For example:

```text
Grass → Caterpillar
```

means that the Caterpillar consumes the Grass.

The simulation therefore follows **directed feeding relationships**, rather than treating the network as an undirected collection of lines.

## 🧠 Why Six Degrees is only the starting point

Six Degrees of Separation gives us an intuitive question:

> **How many connections separate two seemingly distant things?**

Watts and Strogatz showed something deeper: a network can have mostly local connections while a relatively small number of long-range connections can dramatically reduce average path length without immediately destroying local clustering.

Small Worlds uses an ecological-looking network as a visual starting point for exploring that mechanism.

It is **not** trying to prove that food webs behave exactly like social networks.

## 🎨 Designed to be understood first

The interface intentionally uses a soft, vintage natural-history aesthetic so the project feels more like an interactive field notebook than a mathematics dashboard.

The intended progression is:

```text
See the organisms
      ↓
Follow a feeding route
      ↓
Measure the distance
      ↓
Test one new connection
      ↓
See whether the route changes
      ↓
Then learn the graph theory behind it
```

## 🧮 Technical foundation

### Shortest path

The network is represented using adjacency sets. Because the feeding graph is unweighted, **Breadth-First Search (BFS)** is used to find shortest directed paths.

### Hypothetical connection

The simulator checks candidate interactions rather than blindly drawing a random edge. A candidate must:

- not already exist,
- satisfy the simplified trophic-role rules used by the toy model,
- connect nodes that are sufficiently separated in the existing topology, and
- genuinely shorten the selected route.

If no candidate satisfies these conditions, the interface reports that **no useful long-range connection exists**.

## 🛠️ Tech Stack

| Part | Technology |
|---|---|
| Interface | HTML, CSS, JavaScript |
| Visualization | HTML Canvas |
| Graph | JavaScript adjacency sets |
| Shortest path | Breadth-First Search (BFS) |
| Deployment | GitHub Pages |
| Version control | Git / GitHub |

## 🚧 Roadmap

- [x] Interactive organism network
- [x] Directed feeding relationships
- [x] Shortest feeding-path exploration
- [x] Hypothetical long-range interaction test
- [x] Explicit no-valid-connection result
- [x] Vintage field-guide interface
- [ ] Network-wide small-world experiment
- [ ] Measure average path length and clustering across many trials
- [ ] Compare the ecological-looking model with the classic Watts–Strogatz network
- [ ] Explore documented real biological interaction data as a future extension

## 📚 References

- Watts, D. J., & Strogatz, S. H. (1998). *Collective dynamics of 'small-world' networks*. **Nature, 393**, 440–442.
- Milgram, S. (1967). *The Small World Problem*. **Psychology Today, 2**, 60–67.

## 💡 The bigger idea

The project begins with organisms because people understand relationships between living things more easily than abstract nodes and edges.

But the real subject is **network structure**:

> **How can a system that is mostly locally connected become surprisingly easy to navigate when only a few distant connections appear?**

That is the question Small Worlds is built to explore.

## License

MIT
