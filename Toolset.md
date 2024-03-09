- GitHub Desktop - https://desktop.github.com/
- Obdisidian Vault - https://obsidian.md/
	- Git tutorial : [obsidian-git-tut-windows/README.md at main · gitobsidiantutorial/obsidian-git-tut-windows](https://github.com/gitobsidiantutorial/obsidian-git-tut-windows/blob/main/README.md)
	- Obsidian-git plugin : https://github.com/denolehov/obsidian-git/wiki/Installation
- Polars
	- Data wrangling library
	- [Polars](https://docs.pola.rs/)
	- [Polars a Superior Choice to Pandas | by Keegan Fernandes | MLearning.ai | Medium](https://medium.com/mlearning-ai/polars-a-superior-choice-to-pandas-1ab310f8de52)
	- [Reading Delta Lake Tables into Polars DataFrames | Delta Lake](https://delta.io/blog/2022-12-22-reading-delta-lake-tables-polars-dataframe/)
	- 
- Benchmarks :
		[Database-like ops benchmark (duckdblabs.github.io)](https://duckdblabs.github.io/db-benchmark/)

- **Vulture (library for dead code detection)**
	- Vulture [jendrikseipp/vulture: Find dead Python code (github.com)](https://github.com/jendrikseipp/vulture)
		- [vulture · PyPI](https://pypi.org/project/vulture/)
		- Examples :

```python
# check file
vulture my_script.py --min-confidence 100
# check directory
vulture directory --min-confidence 100
```

- **TOX**
	- [User Guide - tox](https://tox.wiki/en/4.12.1/user_guide.html)
	- Tox is an environment orchestrator. Use it to define how to setup and execute various tools on your projects.
	- Steps to setup:
		- Install TOX ```pip install tox```
		- Create in the repository (parent directory) the following file **'tox.ini'**
		- Simple usage :
		
```
[tox]  
requires =  
    tox>=4  
env_list = lint, type, py{38,39,310,311}  
  
[base]  
databricks_deps =  
    -r{toxinidir}/databricks/requirements_dev.txt  
  
[testenv:reformat]  
description = Run reformat tooling  
deps = {[base]databricks_deps}  
  
setenv =  
    PYTHONPATH=./databricks/src  
    SPARK_LOCAL_IP=127.0.0.1  
allowlist_externals =  
    black  
  
commands =  
    isort --profile black databricks  
    black --line-length=120 databricks
```

# Tags
#tox, 