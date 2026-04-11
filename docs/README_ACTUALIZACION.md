# Qué copiar en tu repo

Copia estos archivos dentro de `docs/`:

- `intro.md`
- `contexto_objetivos.md`
- `marco_metodologia.md`
- `conclusiones.md`
- `_toc.yml`
- `_config.yml`

# Qué cambiar dentro de los notebooks

En `univariado.ipynb`, `bivariado.ipynb` y `multivariado.ipynb`, reemplaza la celda que lee el CSV por esto:

```python
from pathlib import Path
import pandas as pd

candidates = [
    Path("NGACOL.csv"),
    Path("docs/NGACOL.csv"),
    Path.cwd() / "NGACOL.csv",
    Path.cwd() / "docs" / "NGACOL.csv",
]

for p in candidates:
    if p.exists():
        data_path = p
        break
else:
    raise FileNotFoundError("No se encontró NGACOL.csv")

print(f"Usando archivo: {data_path.resolve()}")
df = pd.read_csv(data_path)
```

# Dependencias mínimas

Asegúrate de tener instalado al menos:

```bash
pip install -U jupyter-book pandas numpy matplotlib seaborn plotly
```

# Compilación local

Desde la raíz del repo:

```bash
jupyter-book build docs/
```

# Publicación con gh-pages

Si tu sitio ya publica desde la rama `gh-pages`, usa:

```bash
pip install -U ghp-import
jupyter-book build docs/
ghp-import -n -p -f docs/_build/html
```

Si GitHub Pages ya está configurado para la rama `gh-pages`, esto actualiza el sitio.
