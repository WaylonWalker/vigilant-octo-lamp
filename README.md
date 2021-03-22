# poor_local_conf

## Overview

This project was created with kedro == 0.17.2. to demonstrate a confusing error message when a `credentials.yml` is poorly configured.

## Error message

Executing `kedro run` results in the following error.


``` python 
2021-03-22 15:49:21,394 - kedro.framework.session.store - INFO - `read()` not implemented for `BaseSessionStore`. Assuming empty store.
2021-03-22 15:49:21,492 - root - INFO - ** Kedro project poor_local_conf
2021-03-22 15:49:21,498 - kedro.framework.session.store - INFO - `save()` not implemented for `BaseSessionStore`. Skipping the step.
Traceback (most recent call last):
  File "/home/kedro/miniconda3/envs/poor-local-conf/bin/kedro", line 8, in <module>
    sys.exit(main())
  File "/home/kedro/miniconda3/envs/poor-local-conf/lib/python3.8/site-packages/kedro/framework/cli/cli.py", line 228, in main
    cli_collection(**cli_context)
  File "/home/kedro/miniconda3/envs/poor-local-conf/lib/python3.8/site-packages/click/core.py", line 829, in __call__
    return self.main(*args, **kwargs)
  File "/home/kedro/miniconda3/envs/poor-local-conf/lib/python3.8/site-packages/click/core.py", line 782, in main
    rv = self.invoke(ctx)
  File "/home/kedro/miniconda3/envs/poor-local-conf/lib/python3.8/site-packages/click/core.py", line 1259, in invoke
    return _process_result(sub_ctx.command.invoke(sub_ctx))
  File "/home/kedro/miniconda3/envs/poor-local-conf/lib/python3.8/site-packages/click/core.py", line 1066, in invoke
    return ctx.invoke(self.callback, **ctx.params)
  File "/home/kedro/miniconda3/envs/poor-local-conf/lib/python3.8/site-packages/click/core.py", line 610, in invoke
    return callback(*args, **kwargs)
  File "/home/kedro/git/poor_local_conf/src/poor_local_conf/cli.py", line 231, in run
    session.run(
  File "/home/kedro/miniconda3/envs/poor-local-conf/lib/python3.8/site-packages/kedro/framework/session/session.py", line 371, in run
    catalog = context._get_catalog(
  File "/home/kedro/miniconda3/envs/poor-local-conf/lib/python3.8/site-packages/kedro/framework/context/context.py", line 374, in _get_catalog
    conf_creds = self._get_config_credentials()
  File "/home/kedro/miniconda3/envs/poor-local-conf/lib/python3.8/site-packages/kedro/framework/context/context.py", line 491, in _get_config_credentials
    conf_creds = self.config_loader.get(
  File "/home/kedro/miniconda3/envs/poor-local-conf/lib/python3.8/site-packages/kedro/config/config.py", line 226, in get
    new_conf = self._load_configs(config_filepaths)
  File "/home/kedro/miniconda3/envs/poor-local-conf/lib/python3.8/site-packages/kedro/config/config.py", line 164, in _load_configs
    single_config = self._load_config_file(config_filepath)
  File "/home/kedro/miniconda3/envs/poor-local-conf/lib/python3.8/site-packages/kedro/config/config.py", line 141, in _load_config_file
    for k, v in anyconfig.load(config_file).items()
AttributeError: 'str' object has no attribute 'items'

```
