# git pre-commit hook

Heavily inspired by [smgladkovskiy/phpcs-git-pre-commit](https://github.com/smgladkovskiy/phpcs-git-pre-commit)

## About

Run php linting, code beautifier and code sniffer automatically to the PS2 standard. This differs from
[smgladkovskiy/phpcs-git-pre-commit](https://github.com/smgladkovskiy/phpcs-git-pre-commit) only in that
it runs `phpcbf` in addition to `phpcs`.

## Install

    composer require --dev "agentsquidflaps/pre-commit"

To enable code sniff, аdd to `post-install-cmd` and `post-update-cmd` in `composer.json` installation script:

    "scripts": {
        "install-hooks": ["sh ./vendor/agentsquidflaps/pre-commit/src/setup.sh"],
        "post-install-cmd": ["@install-hooks"],
        "post-update-cmd": ["@install-hooks"]
    }

Then run `composer install` or `composer update`. `pre-commit` hook will be installed or updated.
