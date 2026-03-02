# Stem Separation Engine

This module uses [SpleeterRT](https://github.com/James-Woodall/SpleeterRT) for real-time stem separation.

## Engine Files

The pre-built engine goes in `engine/spleeter-move/`:

```
engine/spleeter-move/
├── spleeter            # SpleeterRT binary (~39MB)
├── libopenblas.so.0    # OpenBLAS runtime (~20MB)
└── libgfortran.so.5    # Fortran runtime (~1.5MB)
```

## Building

### Option 1: Docker build (recommended)
```bash
# Clone SpleeterRT to engine/SpleeterRT/ and add Dockerfile.move
./scripts/build.sh --docker
```

### Option 2: Pre-built engine
```bash
# Copy pre-built output to engine/spleeter-move/
cp -r /path/to/spleeter-move engine/
./scripts/build.sh
```

## Output

SpleeterRT separates audio into 3 stems:
- drums
- vocals
- accompaniment

Runs at ~0.5x realtime on Move's Cortex-A72.
