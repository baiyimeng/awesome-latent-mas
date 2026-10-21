# Contributing

Thank you for helping maintain Awesome Latent Multi-Agent Systems. Suggestions, metadata corrections and improvements to the classification are welcome.

## What belongs here

A submission must satisfy both conditions:

1. **Multi-agent:** the paper designs, evaluates or analyzes a system with at least two collaborating logical agents. Shared model weights and one-way communication are allowed.
2. **Latent:** continuous representations play a substantive role in reasoning or cross-agent information exchange. Examples include soft embeddings, hidden activations, Transformer KV caches and learned communication codes.

Eligible mechanisms include agent-local continuous reasoning within a MAS, cross-agent exchange of internal representations, and cross-agent state reuse. Describe agent-local reasoning and inter-agent communication separately, according to where the latent states are used.

Analysis, negative results and safety studies are welcome when they directly investigate latent multi-agent systems. Inclusion is not an endorsement of every claim or a claim of independent reproduction.

## Choose a category

All papers sit under **Papers**. **Communication Methods** contains the three state-origin categories below; **Analysis and Safety** and **Application Studies** are sibling sections within Papers.

Classify the **inference-time source of the communicated states**, not the title, carrier, training target, or claimed speedup:

- **Context-Encoding State Transfer:** exposes states formed while reading existing inputs. Generic cross-agent reuse of shared-context caches belongs here.
- **Text-Generation State Transfer:** exposes states from discrete plan or reply generation, including decoding-to-prefill KV reuse. Discrete diffusion is a token-generation process; identify it explicitly.
- **Direct Latent-Message Generation:** produces continuous positions or dedicated continuation blocks without first producing the corresponding text. Include autoregressive latent rollout and parallel state writers.

A method can have more than one variant. Give the paper one full entry under its primary described mechanism and add a short cross-reference for another verified variant. Count publications once. A prompt-plus-latent KV cache belongs with direct generation when the new latent positions are the defining contribution. Compressing existing input states alone remains context encoding.

“KV”, “hidden”, “hybrid”, “heterogeneous”, “training-free”, “compression”, and “cache reuse” are attributes, not interchangeable categories. Use **Application Studies** only for a verified multi-agent latent system whose accessible primary source does not establish its state-generation path; explicitly state the evidence limit rather than guessing. Analysis and safety papers have their own section.

## Add an entry

Use this format, keeping the description to one or two concrete sentences:

```markdown
- **[Full Paper Title](PAPER_URL)** — **Short Name**.
  `YYYY-MM-DD` · Verified venue or arXiv · [Code](OFFICIAL_CODE_URL).
  Explain what the agents exchange, how the state is produced, and what the method changes.
  <sub>Carrier · Model compatibility · Training, where established</sub>
```

- Use the arXiv **v1 submission date**, and sort newest first within the category. Do not infer a date from the arXiv identifier or use a later revision date.
- If no arXiv record exists, use a verified paper-specific acceptance date and label it. Otherwise use the proceedings date at its published precision, explicitly marked `proceedings`; never substitute a conference-wide notification deadline.
- Verify acceptance through proceedings, the paper, an official program, or an author-maintained source. Label workshops and Findings explicitly. “Under review” is not acceptance. Use `arXiv` when no venue is asserted.
- Prefer the paper landing page and official code. Label unofficial and reference implementations. Omit an unverified code link rather than inventing one.
- Preserve a paper's title. Note a different proceedings title when relevant.
- Compatibility tags describe evaluated setups. Same model family does not guarantee compatible states; heterogeneous support does not imply zero-shot transfer to arbitrary unseen model pairs.
- Describe training precisely. Calibration and closed-form fitting are not gradient training; an interface-only update is not full-model fine-tuning.
- Do not copy full abstracts, benchmark tables or paper figures. The README uses short original summaries and one original taxonomy diagram.

## Submit a change

Open a focused pull request, or use the paper-suggestion or correction issue form. Include a link to the **method section or code** that supports the classification, and briefly identify the participating agents. For a metadata change, link the source of the corrected date, title or venue.

Before submitting, check the Markdown preview, links, ordering, and whether the paper already appears elsewhere. Update the paper-count badge when adding or removing a publication. Keep research scratch files, downloaded papers, screenshots and generated previews out of the repository.
