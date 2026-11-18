# Static Negative Sources and Loss Candidate Sets in Tool Retrieval with Small Dense Encoders

This CPS5801 repository distributes the original experiments and the candidate-set follow-up as one [source archive](CPS5801_Source.zip). Download and extract the archive before running the commands below. The root README and the follow-up README **inside the archive** give the detailed setup, data sources, hardware assumptions, training and evaluation instructions.

## Quick start

From the extracted directory, with Python 3.12 or 3.13:

```sh
python scripts/check_repository.py
python scripts/rebuild_primary_tables.py --output _work/primary_stdlib --no-bootstrap
python followup/check_primary.py
```

These CPU checks validate frozen sources and saved retrieval rankings, reconstruct the original mean results, and recompute the follow-up interaction. They do not retrain neural models. The expected BFCL live interaction is **+0.01750794**, positive in four of five paired seeds. Random negatives still outperform static BM25 negatives on average in both training objectives.

## Where to look after extraction

| Directory or file | Contents |
|---|---|
| `configs/`, `requirements/` | Model and dataset revisions, original training configurations, GPU and analysis requirements |
| `frozen/`, `scripts/` | Scientific source, data setup, training, evaluation, and reconstruction scripts |
| `followup/` | Fixed E5 plan, 20 training configurations, masked-batch objectives, evaluations, per-seed evidence and manuscript tables |
| `results/`, `validation/`, `provenance/` | Rank-only representative data, verification records, hashes and source mapping |
| `AI_DISCLOSURE.md`, `followup/README.md`, `THIRD_PARTY_NOTICES.md` | Assistance, annotation provenance and upstream attribution |

Training used an NVIDIA RTX A5000. Obtain datasets and pretrained models using the pinned identifiers and acquisition instructions in the extracted README. Exact replay of the historical training and evaluation pipeline requires the matching frozen inputs; the public archive does not redistribute restricted historical snapshots, private reviewer records, checkpoints, or embeddings. Rebuilding from upstream sources is not a guarantee of bit-identical replay.
