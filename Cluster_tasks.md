To create virtual environment, 
```bash
uv venv --python 3.xx env_name
source env_name/bin/activate
uv pip install package_to_be_installed
```

To add python kernel:
```bash
uv pip install ipykernel
python -m ipykernel install --user --name=display_name
```
