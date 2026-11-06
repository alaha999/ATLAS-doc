# Git Tags for LLMETanalysis Production

This guide explains how to tag a specific repository version for grid production and reproduce it later.

## 1. Commit Final Changes

Ensure all analysis code, YAML configurations, and dataset lists are committed.

```bash
git status
git add .
git commit -m "Finalize LLMETRun2v2 production"
git push
```

If Easyjet was modified, commit and push those changes in its repository first, then commit the updated submodule reference in the main repository.

## 2. Check the Working Tree Before Tagging

Verify that no uncommitted changes remain:

```bash
git status --short
```

**Expected output:** Nothing.

For an automatic check that stops if the working tree is not clean:

```bash
if [[ -n "$(git status --porcelain)" ]]; then
    echo "ERROR: Working tree is not clean. Commit or stash changes first."
    exit 1
fi

echo "Working tree is clean. Ready to tag."
```

Also check the Easyjet submodule:

```bash
git -C easyjet status --short
```

Ensure this returns no output and that any required Easyjet commits have been pushed to their remote.

## 3. Create and Push a Production Tag

Create an annotated tag:

```bash
git tag -a LLMETRun2v2 \
    -m "LLMETRun2v2 production - AthAnalysis 25.2.113"
```

Push the tag to GitLab:

```bash
git push origin LLMETRun2v2
```

The tag will appear under **GitLab → Repository → Tags**.

## 4. Verify the Tag

```bash
# List available tags
git tag -n

# Show tag information
git show LLMETRun2v2 --no-patch

# Show exact production commit
git rev-parse 'LLMETRun2v2^{commit}'

# Show recorded Easyjet submodule commit
git ls-tree LLMETRun2v2 easyjet
```

## 5. Reproduce the Production Later

Clone the tagged version, including submodules:

```bash
git clone --branch LLMETRun2v2 --recurse-submodules <repository-url>
cd llmet-analysis-easyjet
```

Alternatively, in an existing clone:

```bash
git fetch origin --tags
git switch --detach LLMETRun2v2
git submodule update --init --recursive
```

Set up the original Athena release:

```bash
setupATLAS
asetup AthAnalysis,25.2.113
```

Follow the repository's build instructions to compile Easyjet and LLMETanalysis.

Use the original run configuration:

```text
LLMETanalysis/RunConfig-LeptonsMET.yaml
```

Submit MC20e using:

```bash
./submit_grid.sh mc20e
```

Ensure the grid campaign and submission options match the original production.

## 6. Future Productions

For each new production version:

```bash
# Commit and push changes
git add .
git commit -m "Finalize LLMETRun2v3 production"
git push

# Check clean working tree
if [[ -n "$(git status --porcelain)" ]]; then
    echo "ERROR: Working tree is not clean."
    exit 1
fi

# Create and push tag
git tag -a LLMETRun2v3 \
    -m "LLMETRun2v3 production - AthAnalysis 25.2.113"

git push origin LLMETRun2v3
```

**Important:** A production tag identifies a committed repository state, including recorded submodule commits. It does not capture uncommitted changes, external software installations, or untracked grid inputs. Never move or overwrite a tag that has already been used for production.