## Local SAM smoke test

To quickly verify that the project builds and the local API starts correctly,
you can run a pyenv-aware smoke test that:

- builds the SAM application
- launches `sam local start-api`
- calls the `/health` endpoint
- fails fast if anything is misconfigured

```bash
make test-local PYENV_ENV=<pyenv-environment-name>
```

Example:

```bash
make test-local PYENV_ENV=rical3-py312
```

This uses `tools/test_local_sam.sh` under the hood and ensures the correct
pyenv environment is active before invoking the SAM CLI.
