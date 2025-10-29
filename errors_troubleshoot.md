
When ```import torch``` causes error ```ImportError: ... libcusparse.so.12: undefined symbol: __nvJitLinkAddData_12_1, version libnvJitLink.so.12```,
the reason is your shell had LD_LIBRARY_PATH pointing to a system CUDA toolkit (i.e., check ```echo $LD_LIBRARY_PATH```).
The dynamic linker picked libnvJitLink from the system instead of the PyTorch wheel. 

To resolve, we have to clear LD_LIBRARY_PATH to let PyTorch use its bundled CUDA libs and import correctly.

Doing this by ```unset LD_LIBRARY_PATH``` before installing with ```uv sync```. 

Then, set jupyter notebook kernel and insert `"/usr/bin/env","-u","LD_LIBRARY_PATH"` as follows: 
```
{ "argv": ["/usr/bin/env","-u","LD_LIBRARY_PATH",
"/data1/.../.venv/bin/python",
"-m","ipykernel_launcher",
"-f","{connection_file}"],
... }
```
In jupyter notebook, check
```python
import os, sys
print("Kernel Python:", sys.executable)
print("LD_LIBRARY_PATH:", os.environ.get("LD_LIBRARY_PATH"))
```
