# Changelog

## [1.1.0](https://github.com/bmmmm/mika-birthday/compare/v1.0.0...v1.1.0) (2026-04-25)


### Features

* 10 themes (dark/light/amber/matrix/blueprint/paper/neon/dos/brutalist/ink) + theme picker in builder ([a98a30a](https://github.com/bmmmm/mika-birthday/commit/a98a30a5aed22fdbafacd0c79bcf2df66760d8b7))
* add donation link to all pages ([0a2cc47](https://github.com/bmmmm/mika-birthday/commit/0a2cc471f1c1597845ec7c417ccb1b972f8dda79))
* add live config panel on card page ([57966db](https://github.com/bmmmm/mika-birthday/commit/57966db6bb521d89eafed47b4b4be62d078ba475))
* add message/quote picker with 11 templates and custom text ([b524a97](https://github.com/bmmmm/mika-birthday/commit/b524a976c3f2109852475a7787bf538146ab232c))
* age badge, locked mode, uwu easter egg, themes, attribution ([5f244ad](https://github.com/bmmmm/mika-birthday/commit/5f244adcc2ac0922c5234fdc10a223a1b39b4f30))
* automate versioning via release-please + Pages workflow ([9594fdb](https://github.com/bmmmm/mika-birthday/commit/9594fdb783923f9c6c160ede6a0063e90ca82839))
* birthday card — generalized ([2e6c3c6](https://github.com/bmmmm/mika-birthday/commit/2e6c3c6710623ae2676452909cc4feaa352be299))
* bottom bar, side panel overhaul, token on card, input validation ([1bd44c3](https://github.com/bmmmm/mika-birthday/commit/1bd44c33413815eec4fe2f90f382a1a9dfab41f9))
* builder — device select, ASCII theme palette, footer; fix device click ([f5bb7f1](https://github.com/bmmmm/mika-birthday/commit/f5bb7f10ed2ab0256966b2a6414401409d8a2bb1))
* builder page + Giphy search (key required, sessionStorage) ([e1cbe40](https://github.com/bmmmm/mika-birthday/commit/e1cbe4031dcce7199e11574c98de421acd700f3e))
* config.sh panel sticky — floats alongside card while scrolling ([bc7e0f7](https://github.com/bmmmm/mika-birthday/commit/bc7e0f71d31d7effa1eb93196d36782929800ca1))
* device photos (Wikimedia CC) + device override in config panel ([dff9997](https://github.com/bmmmm/mika-birthday/commit/dff99970d8e2622ec2db1cf87f38098229e7fbcf))
* landing page with birthday token system + sneaky hint on locked cards ([22940ea](https://github.com/bmmmm/mika-birthday/commit/22940ea086d3463502addf49c22bb3e5d4722dfb))
* link footer version to GitHub releases page ([0396c7b](https://github.com/bmmmm/mika-birthday/commit/0396c7b5be85fe5ff23f6d1c4ca52ab20024b82d))
* meme picker modal — upload / url / giphy search ([86d67d7](https://github.com/bmmmm/mika-birthday/commit/86d67d74fa139cde96602d31055d726d73eef978))
* modular device config — individual JSON files + config.js ([7407749](https://github.com/bmmmm/mika-birthday/commit/74077498b1dd640c9641474739cb5d0cee9de6e3))
* plain.html — bare ASCII template, zero dependencies ([a2fd89c](https://github.com/bmmmm/mika-birthday/commit/a2fd89ccd22989fe66f729148b8e9a46281af709))
* print fits one A4 page; PDF filename from name+age ([0b2d715](https://github.com/bmmmm/mika-birthday/commit/0b2d715adafe28a9fdd5e8f5c12251e7d776eb82))
* remove Google Fonts, add simple theme, fix meme persistence ([92ff205](https://github.com/bmmmm/mika-birthday/commit/92ff20542ee48d4915d13f0f3a92aaaa2556a67f))
* remove image button + themed meme placeholders ([34495e9](https://github.com/bmmmm/mika-birthday/commit/34495e9dfd8b77aa6e5c948f8ef33683d2b2c379))
* responsive layout, print QR code, window-size compat ([47a7235](https://github.com/bmmmm/mika-birthday/commit/47a7235f867acf2434191e64ff300040253fb54d))
* share/print in config.sh panel; scroll restore; fix toast ([e2e1dab](https://github.com/bmmmm/mika-birthday/commit/e2e1dabdbd6d826cd49de20f887fa4b9c52cee36))
* show device thumbnail in device-badge ([ac35ca4](https://github.com/bmmmm/mika-birthday/commit/ac35ca48c4cc752070f9d7c88ae9ce6f25855672))
* staged image upload with compression + bug fixes ([3b83891](https://github.com/bmmmm/mika-birthday/commit/3b8389197d406c48e147828b2126e6687d6db98d))


### Bug Fixes

* 5 bugs found in review ([ebd6c6f](https://github.com/bmmmm/mika-birthday/commit/ebd6c6fda005cb6bd8f16a25d1be8bce1ca31743))
* **brutalist:** readable hover + extra brutality on bottom-bar buttons ([70e5721](https://github.com/bmmmm/mika-birthday/commit/70e5721c70ba1bc546a63ccad3cfe72349844d20))
* donation link — "plzzz donate kkthx" is the link, no URL shown ([9c5692c](https://github.com/bmmmm/mika-birthday/commit/9c5692c86d80702ed2f45a5b64d9b4e02b31d976))
* improve text contrast across all themes ([7756288](https://github.com/bmmmm/mika-birthday/commit/77562886fe6be1b17568995e86245dbb0974850f))
* move meme-label below image instead of overlaying it ([01fe6a0](https://github.com/bmmmm/mika-birthday/commit/01fe6a055c93696656238990b5bdc3c33fe7bb3e))
* plain.html used dev.label which doesn't exist — changed to dev.shortName. ([7407749](https://github.com/bmmmm/mika-birthday/commit/74077498b1dd640c9641474739cb5d0cee9de6e3))
* print — preserve theme colors, eliminate second page ([0be1b49](https://github.com/bmmmm/mika-birthday/commit/0be1b4999fe9d64fa3a952f8a933e7a2310cc7d3))
* print backgrounds, token full display, footer cleanup ([06000c1](https://github.com/bmmmm/mika-birthday/commit/06000c1af6a36caa042b46aba706aa2dcf333c1f))
* print layout fits 1 page, no more zoom, full width ([26359b3](https://github.com/bmmmm/mika-birthday/commit/26359b32e03f7cbf7aee7e1fa675417dac2b4f17))
* remove Simple theme, fix FOUC on light theme reload, theme-aware hovers ([b1c809d](https://github.com/bmmmm/mika-birthday/commit/b1c809dd03083b1722dce0e3b89a12de5670bf16))
* restore github link in attribution on all pages ([859457d](https://github.com/bmmmm/mika-birthday/commit/859457d63de27d3049eea1aa7d0ccea485cfbc7b))
* restore UI scale before first paint to stop reload wobble ([c6d70d8](https://github.com/bmmmm/mika-birthday/commit/c6d70d85ddbdb0fcb6a434ae2fa3733c04e78bcf))
* show correct buttons in upload stage based on file size ([e792eee](https://github.com/bmmmm/mika-birthday/commit/e792eee9b79e99894d38bd6745935ea4e8c78a6e))
* url tab is default in meme picker, upload moved to second position ([6d326d9](https://github.com/bmmmm/mika-birthday/commit/6d326d95fe907980e839310cd4b7ab6a2672f983))
* validate ranges, token separators, and loader fallbacks ([e581bd0](https://github.com/bmmmm/mika-birthday/commit/e581bd071683f022e7fd4aee2f0bf83be3116efa))

## Changelog
