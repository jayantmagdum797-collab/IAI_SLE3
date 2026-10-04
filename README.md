# IAI_SLE3
# SLE-3: Architectural Design using Full C4 Model

Course: 02AML204 - Introduction to Artificial Intelligence
Name: Jayat Uttam Magdum | PRN: 25UAM135 | Division: B

## About
This SLE documents the architecture of my Route-Finding System (BFS / DFS) from SLE-2 using all 4 levels of the C4 model: Context, Container, Component and Code.

The system takes a graph (adjacency list), a start location A and a destination H. It runs BFS or DFS and returns the route and the number of nodes expanded.

## C4 Levels

### Level 1 - Context
User -> Route-Finding System -> Route output
The system uses the Python runtime (time.perf_counter, matplotlib).

### Level 2 - Container
- Input Module: takes the graph, start and goal
- Search Engine: runs bfs() / dfs()
- Visited Set + Parent Map: avoids loops and stores parents to rebuild the route
- Profiler: measures run time and counts nodes expanded
- Output Module: shows route, tables and charts

### Level 3 - Component (Search Engine)
- Frontier: queue (BFS) / stack (DFS)
- Goal Test: checks if the node is the destination
- Neighbour Expander: reads neighbours from the adjacency list
- Explored Check: skips visited nodes
- Path Reconstructor: builds the route from H back to A using the parent map

### Level 4 - Code
- build_graph(): creates the adjacency-list graph
- bfs(graph, start, goal): queue-based search
- dfs(graph, start, goal): stack/recursion-based search
- reconstruct_path(parent, goal): rebuilds the route
- profile_run(): measures average time
- plot_graph() / plot_chart(): draw the graph and timing chart

## Design Decisions
- 5 containers, each with one job, to keep the design simple and readable
- Profiler kept separate so timing does not change the search code
- Parent map stored during search, so the route is rebuilt only once at the end
- BFS and DFS differ only in the Frontier, which makes the comparison fair

## Files
- SLE3_25UAM135_JayatMagdum.docx : SLE-3 report with C4 diagrams
- route_finding.py : BFS / DFS code from SLE-2

## AI Contribution
- AI used: Claude (Anthropic)
- AI helped with: drawing the diagrams, report layout, first draft of explanations
- I did myself: chose the system, checked containers, components and function names against my code, reviewed everything and can explain the design
