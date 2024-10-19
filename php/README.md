# php

This service is configured to look for your PHP files in `./www/html/`. Therefore you will need to create the `./www/html/` directory and add your PHP files there (e.g. `./www/html/index.php`).

In order to maintain the idempotency of the `docker-containers` repo, all contents inside the `./www/` directory are gitignored. Therefore, you may want to create your project directory somewhere else, create a Git repo for it, then hardlink that project to `./www/html/`. This will allow you to backup the contents of your repo without contaminating this generic Docker container repo.
