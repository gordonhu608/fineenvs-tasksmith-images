# fineenvs-tasksmith-images

Builds the container images of the 39 CPU tasks of [FineEnvs/HF_ML_Tasksmith](https://huggingface.co/datasets/FineEnvs/HF_ML_Tasksmith)
(revision `3c63c8b059d734fe74f932101f44dd0b16e7ee26`, `tasks.tar.gz` sha256 `7ecd4d7a…0f13f80`) and pushes them to
`ghcr.io/gordonhu608/fineenvs-tasksmith`: `<task>-env` from `environment/` (the agent's sandbox) and `<task>-verifier`
from `tests/` (the separate verifier), linux/amd64. Used for RL training on AgentENV, which can only cold-start images
it can pull; the tasks are pinned to these images by digest.

Run: Actions → build → Run workflow. Each job writes `digests/<task>.json`; the `collect` job uploads `images.json`
(task → env / verifier `repo:tag@sha256`). The tasks keep their own licenses (the dataset's LICENSES.md).
