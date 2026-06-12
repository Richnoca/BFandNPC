# BFandNPC
This is a repository for Bellman-Ford Algorithm and proof for proving that 3COLOR is NP-Complete.

# Bellman-Ford
-Writeup explaining when to use Bellman-Ford vs Dijkstra, and discussing the negative cycle detection mechanism

Bellman-Ford algorithm and Dijkstra's algorithm are similar in the fact that they are both used to find shortest paths in a weighted graph. However, 
they both are useful in their own specific situations. Dijkstra's is generally more useful (efficient and faster) when all of the edges are known to be at least zero, meaning all are at least positive. Bellman-Ford is slower than Dijkstra's, however it is a lot more flexible than it because it can be used to handle graphs where not all the weighting is known, or that it is known that there are edges with a negative weight, making it better for a graph that could have negative costs that Dijkstra's wouldn't be able to handle.

As discussed in the previous paragraph, Bellman-Ford can handle and detect negativity. Part of that negativity includes negative cycles. Negative cycles are where the total weight of the cycle from all vertices ends up being less than zero. If a negative cycle is reachable from the source, then a shortest path doesn't exist because the path cost can infinitely decrease each time the cycle repeats on itself, trying to find a more efficient cycle. What Bellman-Ford will do is relax all edges V - 1 times (vertices minus 1, or the number of total edges). Then after that relaxation, it will perform an extra pass through all do the edges. If any distance can be improved from the extra pass then the graph contains a negative cycle that is reachable.
