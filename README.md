# Reading the Genome with HyenaDNA

COMP 565, McGill University — Assignment 3.

Explores **HyenaDNA**, a long-context genomic language model, by asking how
much pre-training helps, what its embeddings encode, and whether it can tell
real DNA from shuffled DNA. Built on the
[HyenaDNA Colab](https://github.com/HazyResearch/hyena-dna) from HazyResearch.

## What's here

1. **Training from scratch vs fine-tuning** — adds a `from_scratch` switch to
   `HyenaDNAPreTrainedModel.from_pretrained`, then trains
   `hyenadna-tiny-1k-seqlen` on the GenomicBenchmarks
   `dummy_mouse_enhancers_ensembl` task both ways and plots test accuracy per
   epoch.
2. **Sequence embeddings** — modifies the inference loop to global-average-pool
   token embeddings into one vector per sequence, for the pre-trained-only,
   fine-tuned and from-scratch models.
3. **t-SNE** — visualizes the three embedding spaces coloured by enhancer label.
4. **Next-nucleotide prediction** — runs the pre-trained model autoregressively
   over the human **ACTB** gene (with promoter and introns) and computes
   perplexity, against a shuffled ACTB sequence as a negative control.

## Files

- `COMP565_A3_HyenaDNA.ipynb` — full notebook with outputs.
- `ACTB_with_promoter_and_introns.fa` — the ACTB sequence used in task 8.

## Running it

Designed for Google Colab with a GPU. The notebook downloads the HyenaDNA
checkpoint and GenomicBenchmarks data itself; upload the FASTA file where the
task 8 cell expects it.

## Author

Andrea Paola Gómez Jaime
