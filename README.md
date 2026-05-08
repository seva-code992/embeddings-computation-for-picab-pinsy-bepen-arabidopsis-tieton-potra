# My Project

In this project the model "mixedbread-ai/mxbai-embed-large-v1" from SentenceTransformers is used to compute embeddings based on gene annotations. 
Annotations downloaded from https://north-1.cloud.snic.se:8080/swift/v1/AUTH_d9d5ac98cb2b4a3091b60040077e8efc/plantgenie-knowledge/, where currently there are gene annotations of 6 species available: 
1) "pinsy" for Pinus sylvestris (Scots pine)
2) "picab" for Picea abies (Norway spruce)
3) "arabidopsis" for Arabidopsis thaliana
4) "potra" for Populus tremula (European aspen)
5) "tieton" for Tilia tomentosa (Silver linden)
6) "bepen" for Betula pendula (Silver birch)

## Features & Requirements
-Python3.12+
-Duckdb
-uv




## Install dependencies
uv pip install -r requirements.txt


## How to use 

git clone https://github.com/seva-code992/embeddings-computation-for-picab-pinsy-bepen-arabidopsis-tieton-potra.git
cd embeddings-computation-for-picab-pinsy-bepen-arabidopsis-tieton-potra

uv venv
source .venv/bin/activate
uv pip install -r requirements.txt
uv run fileprep.py

duckdb database.db
duckdb database.db -f export_modified_tables.sql

## To save embeddings for each species: 

uv run pinsy_embeddings.py
uv run potra_embeddings.py
uv run picab_embeddings.py
uv run bepen_embeddings.py
uv run tieton_embeddings.py
uv run arabidopsis_embeddings.py


## License

MIT
