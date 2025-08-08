<img width="652" height="327" alt="image" src="https://github.com/user-attachments/assets/90c09d13-e648-41e6-940c-41aa7eeba223" />

If you are going to be creating evals, we suggest cloning this repo directly from GitHub and installing the requirements using the following command:

```sh
pip install -e .
```

Using `-e`, changes you make to your eval will be reflected immediately without having to reinstall.

Optionally, you can install the formatters for pre-committing with:

```sh
pip install -e .[formatters]
```

Then run `pre-commit install` to install pre-commit into your git hooks. pre-commit will now run on every commit.

If you want to manually run all pre-commit hooks on a repository, run `pre-commit run --all-files`. To run individual hooks use `pre-commit run <hook_id>`.
