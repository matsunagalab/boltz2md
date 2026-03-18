## from Boltz-2 to MD

```
uv venv --python=python3.11
source .venv/bin/activate
uv pip install boltz -U
uv pip install pdbfixer
```

```
boltz predict 4idl_contact.yaml --use_msa_server --use_potentials --override --output_format pdb
```

```
less 1_build.py
```

```
python 1_build.py
pymol system.pdb
```

```
python 2_equilibration.py
pymol -d "load system.pdb, run, 0, pdb; load_traj 2_equilibration.dcd;"
```

```
python 3_production.py
pymol -d "load system.pdb, run, 0, pdb; load_traj 3_production.dcd;"
```

```
deactivate
```
