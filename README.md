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
- structured data processing (obviously)

Multigraph neural networks enable doing really cool things like
- Storing recurrent state information in a backpropagatable graph
- Dynamically structuing chain graphs (phrases and sentences) into thought graphs

What this is not
- A framework for artificial general intelligence. It may be useful though
- A tool for managing large graphs (>30 nodes). Although storing fully dense adjacency matricies has its computation and memory costs, it allows gradients to propagate directly to their targets. 
