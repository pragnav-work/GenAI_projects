# FAISS Semantic Search — Theory Answers

## Q1. What is the difference between `IndexFlatL2` and `IndexFlatIP` in FAISS? When would you use each?

`IndexFlatL2` searches vectors using L2 (Euclidean) distance. It measures the geometric distance between two vectors, where a smaller distance indicates greater similarity.

`IndexFlatIP` searches vectors using inner product (dot product). A larger inner product indicates greater similarity.

For normalized vectors, inner product is equivalent to cosine similarity because both vectors have a magnitude of 1.

### When to use each

- Use `IndexFlatL2` when Euclidean distance is the desired distance metric.
- Use `IndexFlatIP` when inner product or cosine similarity is required.
- For cosine similarity, embeddings can be normalized and searched using `IndexFlatIP`.

In this project, `IndexFlatL2` was used with normalized embeddings. This makes the L2 distance suitable for ranking vectors according to cosine similarity.


## Q2. Why do we normalise embeddings before adding to FAISS when we want cosine similarity?

Cosine similarity measures the angle between two vectors rather than their magnitude.

The cosine similarity between two vectors is:

`cosine similarity = (A · B) / (||A|| ||B||)`

When both vectors are normalized to unit length:

`||A|| = ||B|| = 1`

the formula becomes:

`cosine similarity = A · B`

For normalized vectors, L2 distance and cosine similarity produce the same ranking because:

`||A - B||² = 2 - 2(A · B)`

Therefore, normalizing the embeddings allows `IndexFlatL2` to approximate the same ranking that would be obtained using cosine similarity.


## Q3. FAISS uses ANN (Approximate Nearest Neighbour) search. What does "approximate" mean here and why is it acceptable?

Approximate Nearest Neighbour (ANN) search means that the system searches for vectors that are very likely to be among the nearest neighbours instead of guaranteeing the mathematically exact nearest neighbours.

The advantage is significantly faster search when working with very large datasets containing millions or billions of vectors.

A small amount of accuracy or recall may be traded for a substantial improvement in search speed and computational efficiency.

This trade-off is acceptable in many real-world applications because retrieving highly relevant results quickly is often more valuable than spending significantly more computational resources to guarantee the exact nearest neighbour.

### Important implementation note

The `IndexFlatL2` index used in this project performs an exact nearest-neighbour search rather than an approximate search. ANN techniques are provided by other FAISS index types, such as IVF and HNSW.

Therefore, the statement that FAISS uses ANN should be understood as referring to FAISS's broader vector-search capabilities rather than specifically to `IndexFlatL2`.