
**Vanilla Attention (Bahdanau et al., 2014)**
[Neural Machine Translation by Jointly Learning to Align and Translate](https://arxiv.org/abs/1409.0473)

- Original seq2seq attention for neural machine translation
- Problem solved: Fixed-length context vectors losing information in long sequences
- Allowed decoder to "look back" at all encoder states

**Multiplicative/Dot-Product Attention (Luong et al., 2015)**
[Effective Approaches to Attention-based Neural Machine Translation](https://arxiv.org/abs/1508.04025)

- Simplified attention with dot products instead of learned weights
- Problem solved: Computational efficiency compared to additive attention
- Made attention faster and simpler to implement

**Self-Attention (Cheng et al., 2016)**
[Long Short-Term Memory-Networks for Machine Reading](https://arxiv.org/abs/1601.06733)

- Attention within a single sequence rather than between encoder-decoder
- Problem solved: Capturing long-range dependencies within text
- Each token attends to all other tokens in the same sequence

**Scaled Dot-Product Attention (Vaswani et al., 2017 - Transformer)**
[Attention Is All You Need](https://arxiv.org/abs/1706.03762)

- Added scaling factor (1/√d_k) to dot products
- Problem solved: Gradient issues when dot products grew too large
- Stabilized training for larger models

**Multi-Head Attention (Vaswani et al., 2017)**
[Attention Is All You Need](https://arxiv.org/abs/1706.03762)

- Multiple attention operations in parallel with different learned projections
- Problem solved: Single attention focuses on one aspect; multi-head captures different relationships simultaneously
- Each head can learn different patterns (syntax, semantics, etc.)

**Sparse Attention (Child et al., 2019)**
[Generating Long Sequences with Sparse Transformers](https://arxiv.org/abs/1904.10509)

- Attention only to subset of positions using fixed patterns
- Problem solved: O(n²) complexity making long sequences infeasible
- Enabled processing of much longer sequences

**Linformer (Wang et al., 2020)**
[Linformer: Self-Attention with Linear Complexity](https://arxiv.org/abs/2006.04768)

- Projects sequence length dimension to lower dimension
- Problem solved: Quadratic complexity in sequence length
- Reduces attention to O(n) complexity

**Performer/Linear Attention (Choromanski et al., 2020)**
[Rethinking Attention with Performers](https://arxiv.org/abs/2009.14794)

- Uses kernel methods to approximate attention
- Problem solved: Full attention matrix computation and storage
- Linear time and space complexity

**Longformer (Beltagy et al., 2020)**
[Longformer: The Long-Document Transformer](https://arxiv.org/abs/2004.05150)

- Combines local windowed attention with global attention on select tokens
- Problem solved: Processing documents of thousands of tokens
- Efficient for document-level tasks

**BigBird (Zaheer et al., 2020)**
[Big Bird: Transformers for Longer Sequences](https://arxiv.org/abs/2007.14062)

- Random attention + window attention + global attention
- Problem solved: Balancing locality and global context efficiently
- Theoretical guarantees on expressiveness

**Synthesizer (Tay et al., 2020)**
[Synthesizer: Rethinking Self-Attention in Transformer Models](https://arxiv.org/abs/2005.00743)

- Learns attention patterns without token-token comparisons
- Problem solved: Questioned whether attention needs to be content-based
- Showed learned patterns can sometimes work as well

**Routing Transformer (Roy et al., 2021)**
[Efficient Content-Based Sparse Attention with Routing Transformers](https://arxiv.org/abs/2003.05997)

- Uses k-means clustering to route similar queries/keys
- Problem solved: Computational cost while maintaining quality
- Clusters enable efficient sparse attention

**Flash Attention (Dao et al., 2022)**
[FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness](https://arxiv.org/abs/2205.14135)

- Reorders attention computation to be IO-aware
- Problem solved: Memory bandwidth bottleneck, not just FLOPs
- 2-4x speedup by optimizing GPU memory access patterns

**Multi-Query Attention (Shazeer, 2019) / Grouped-Query Attention (Ainslie et al., 2023)**
[Fast Transformer Decoding: One Write-Head is All You Need](https://arxiv.org/abs/1911.02150) / [GQA: Training Generalized Multi-Query Transformer Models from Multi-Head Checkpoints](https://arxiv.org/abs/2305.13245)

- Shares key/value heads across multiple query heads
- Problem solved: KV cache size during inference
- Enables faster inference with minimal quality loss

**Flash Attention 2 (Dao, 2023)**
[FlashAttention-2: Faster Attention with Better Parallelism and Work Partitioning](https://arxiv.org/abs/2307.08691)

- Further optimizations with better parallelism and work partitioning
- Problem solved: Scaling to longer sequences and larger batches
- Up to 2x faster than Flash Attention 1

**Sliding Window Attention (Mistral, 2023)**
[Mistral 7B](https://arxiv.org/abs/2310.06825)

- Fixed-size local attention window
- Problem solved: Infinite theoretical context with bounded computation
- Used in models like Mistral for efficient long-context handling

**Ring Attention (Liu et al., 2023)**
[Ring Attention with Blockwise Transformers for Near-Infinite Context](https://arxiv.org/abs/2310.01889)

- Distributes sequence across devices with blockwise communication
- Problem solved: Sequence length limited by single device memory
- Enables million+ token contexts across multiple GPUs
  