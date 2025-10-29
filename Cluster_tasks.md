To create virtual environment, 
```bash
uv venv --python 3.xx env_name
source env_name/bin/activate
uv pip install package_to_be_installed
```
To install pip
```bash
uv pip install --python .venv pip
```

To add python kernel:
```bash
uv pip install ipykernel
python -m ipykernel install --user --name=display_name
```

To check torch and cuda version: 
```python
# Torch and CUDA info
import torch

print("Torch version:", torch.__version__)              # e.g., '2.3.0+cu121' or '2.3.0+cpu'
print("Built with CUDA:", torch.version.cuda)           # e.g., '12.1'; None for CPU-only builds
print("cuDNN version:", torch.backends.cudnn.version()) # None if not available

print("CUDA available at runtime:", torch.cuda.is_available())
if torch.cuda.is_available():
    print("GPU device count:", torch.cuda.device_count())
    print("Current device:", torch.cuda.current_device())
    print("Device name 0:", torch.cuda.get_device_name(0))
```
or in bash, under the active environment
```bash
pip list | grep -E 'torch|cuda|cudnn'
```
To install correspondingly: 
```bash
uv pip install torch==2.8.0 --index-url https://download.pytorch.org/whl/cu128
```
