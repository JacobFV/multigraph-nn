# multigraph-nn
One isn't enough. Multigraph neural networks are the way to go!

**SUPPORT FOR CODE IN THIS REPOSITORY HAS BEEN DISCONTINUED** I recomment [Deep Graph Library](https://www.dgl.ai/).

## Cool features
- typed nodes and edges
- ready built and customizable pooling operators (multihead attention, convolution, or dense filtering)
- edge updates too!
- sparse intergraph connections with different parameters
- dense intragraph connections let backpropagation learn to dynamically build graphs!

This neural networks tries to make an overreaching framework for processing
- graph2node, node2graph, graph2graph
- seq2vec, vec2seq, seq2seq,
- grid structured data (like 2D convolution)
- learning structure for unstructured data
- structured data processing (obviously)

Multigraph neural networks store recurrent state information in a backpropagatable graph. This prior might enable learning really cool things like
- dynamically restructure chain graphs (phrases and sentences) into thought graphs by autoencoding
- managing a 7±2 element short-term memory grpah for RL agents
- how to compress and uncompress a large graph into a smaller graph

Wouldn't it be cool to watch a string-like sentence graph fold onto itself into some complex looking thought graph?

What this is not
- A framework for artificial general intelligence. It may be useful though
- A tool for managing large graphs (>30 nodes). Although storing fully dense adjacency matricies has its computation and memory costs, it allows gradients to propagate directly to their targets. 

## Getting Started

1. Download and unzip the repository
2. Move your working directory to `multigraph-nn`
3. For a ready made example, run `python3 src/recurrent_multigraph_net.py`. You may be able to modify this example to suite your applications. 

Alternatively, you can use it in your own projects by 
4. Launch jupyter notebook or open your favorite Python IDE
5. type `import src as multigraph_nn`
6. start building exotic neural networks!

## Details

multigraph-nn present a combinatorial suite of tools for quickly building any traditional graph neural network as well as creating new ones. 
- A `Multigraph` is used for all tensor information storage. A `Multigraph` may have zero or one edge and adjacency matrices for each unique (source subgraph, destination subgraph) pair. All graph data is stored in dense matrices.
- A `Multigraph` is updated by a `MultigraphLayer` which may contain zero or more `GraphLayers` for each (source subgraph, destination subgraph) pair.
- A single `GraphLayer` allows arbitrary choice of input processing, pooling, vertex updating, edge updating, and adjacency matrix update functions.
- Input processing functions `f_inp*` select what information to pass on to a graph's individual verteces. In many cases, you want both edge and previous node information, so select `f_inp_concat`. Alternatively to only use edge or vert information, select `f_inp_edges` or `f_inp_verts` respectively.
- Pooling functions `f_pool*` pool information individually for each vertex. 
- Vertex, edge, and adjacency update functions `f_v_up*`, `f_e_up*`, `f_adj_up*` perform vertex, edge, and adjacency updates respectively. If no update is necesary (fixed graph topology for example), they may be identity functions.
- 
