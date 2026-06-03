# Changelog

## [1.1.0](https://github.com/bmmmm/mika-birthday/compare/v1.0.0...v1.1.0) (2026-06-03)


### Features

* 10 themes (dark/light/amber/matrix/blueprint/paper/neon/dos/brutalist/ink) + theme picker in builder ([348e06c](https://github.com/bmmmm/mika-birthday/commit/348e06c489feed7f68c6645ae20b09d18eac79d7))
* add donation link to all pages ([479fddf](https://github.com/bmmmm/mika-birthday/commit/479fddfb58590b2700daabccea64777f48fe376d))
* add live config panel on card page ([ad4801e](https://github.com/bmmmm/mika-birthday/commit/ad4801ef6eb14af73f280c93f4ae89421535a8b2))
* add message/quote picker with 11 templates and custom text ([7b37a73](https://github.com/bmmmm/mika-birthday/commit/7b37a73c6836a6baccc272594b3405b6ac6e8898))
* age badge, locked mode, uwu easter egg, themes, attribution ([42acba6](https://github.com/bmmmm/mika-birthday/commit/42acba6854573b6ee8ab640a4527410e945b8492))
* automate versioning via release-please + Pages workflow ([7465bd8](https://github.com/bmmmm/mika-birthday/commit/7465bd823afe8f02f8b08b5a7723e4b12119cdaa))
* birthday card — generalized ([0296a48](https://github.com/bmmmm/mika-birthday/commit/0296a48173c88966bf52a314a997760930280e7f))
* bottom bar, side panel overhaul, token on card, input validation ([206124b](https://github.com/bmmmm/mika-birthday/commit/206124b0f1524c045f2c55921713541a2605daa7))
* builder — device select, ASCII theme palette, footer; fix device click ([fcbb757](https://github.com/bmmmm/mika-birthday/commit/fcbb7578b396ac9c588e5d401b08907916911bff))
* builder page + Giphy search (key required, sessionStorage) ([bd8df00](https://github.com/bmmmm/mika-birthday/commit/bd8df00d9184e5171052c3221ae90329ea570e18))
* config.sh panel sticky — floats alongside card while scrolling ([ce12e62](https://github.com/bmmmm/mika-birthday/commit/ce12e62849ff503594bc21d8e67841174597641e))
* device photos (Wikimedia CC) + device override in config panel ([c9988bb](https://github.com/bmmmm/mika-birthday/commit/c9988bb2aca772b3c1b41b4f988c35a642f6618b))
* landing page with birthday token system + sneaky hint on locked cards ([af93f1c](https://github.com/bmmmm/mika-birthday/commit/af93f1c01795a8a49227a1e7d0ce5a0406c911fc))
* link footer version to GitHub releases page ([a57e028](https://github.com/bmmmm/mika-birthday/commit/a57e028b3e6be7ede31d5e4e4268648a514e875b))
* meme picker modal — upload / url / giphy search ([baf8793](https://github.com/bmmmm/mika-birthday/commit/baf879388aa0464cc86138cf3aaabaac124396ac))
* modular device config — individual JSON files + config.js ([15b024b](https://github.com/bmmmm/mika-birthday/commit/15b024b1c125d7305d0bbf53f58ed998243133ee))
* plain.html — bare ASCII template, zero dependencies ([dec5627](https://github.com/bmmmm/mika-birthday/commit/dec56275ecf55e7badceeb7d6674c1306f0b17b5))
* print fits one A4 page; PDF filename from name+age ([fc2f491](https://github.com/bmmmm/mika-birthday/commit/fc2f491dc2b352cad640abbea67492374906b9e1))
* remove Google Fonts, add simple theme, fix meme persistence ([2961b5f](https://github.com/bmmmm/mika-birthday/commit/2961b5f02753280caab17932e4aec31c0113887d))
* remove image button + themed meme placeholders ([fa3c9fb](https://github.com/bmmmm/mika-birthday/commit/fa3c9fb9c5bde7aa92832f770990a5cfd8ec52f7))
* responsive layout, print QR code, window-size compat ([9c27ed3](https://github.com/bmmmm/mika-birthday/commit/9c27ed3e1ae39ca600b644debb7e7d655d379082))
* share/print in config.sh panel; scroll restore; fix toast ([7756754](https://github.com/bmmmm/mika-birthday/commit/7756754858a4c6ff10ed6328b12c3f9825819d80))
* show device thumbnail in device-badge ([ba948db](https://github.com/bmmmm/mika-birthday/commit/ba948dbed150f101dd1fb978ceb10834cd355340))
* staged image upload with compression + bug fixes ([2cf3d32](https://github.com/bmmmm/mika-birthday/commit/2cf3d322df97ce625e7d91a08cdd210ee0e5be95))


### Bug Fixes

* 5 bugs found in review ([a2aea39](https://github.com/bmmmm/mika-birthday/commit/a2aea39a7585c120f3c70eae444cd1839543d53b))
* **brutalist:** readable hover + extra brutality on bottom-bar buttons ([f846636](https://github.com/bmmmm/mika-birthday/commit/f84663629cd769f7546d1652aa0ccc93901b26ff))
* donation link — "plzzz donate kkthx" is the link, no URL shown ([45099b9](https://github.com/bmmmm/mika-birthday/commit/45099b973162377865763e46b6ecd5cea1a11e17))
* harden token codec and align param/render across pages ([eeb6eb6](https://github.com/bmmmm/mika-birthday/commit/eeb6eb643e0f5ac398ea808c817ceb8af00c9749))
* improve text contrast across all themes ([2baddea](https://github.com/bmmmm/mika-birthday/commit/2baddea9ce43fe4c72b841ad5400fb664020b3ec))
* move meme-label below image instead of overlaying it ([98ac6c8](https://github.com/bmmmm/mika-birthday/commit/98ac6c8f6807d5d10a5ae54c40db55e0b050896a))
* plain.html used dev.label which doesn't exist — changed to dev.shortName. ([15b024b](https://github.com/bmmmm/mika-birthday/commit/15b024b1c125d7305d0bbf53f58ed998243133ee))
* print — preserve theme colors, eliminate second page ([06325be](https://github.com/bmmmm/mika-birthday/commit/06325be51dcf484ffbee705ca112b27a522870bd))
* print backgrounds, token full display, footer cleanup ([23584b8](https://github.com/bmmmm/mika-birthday/commit/23584b8617a1c32072b4d51e587411c525b439ca))
* print layout fits 1 page, no more zoom, full width ([3e1fb69](https://github.com/bmmmm/mika-birthday/commit/3e1fb69d40d39ecb92a59955d54e58e118d37a15))
* remove Simple theme, fix FOUC on light theme reload, theme-aware hovers ([269a16a](https://github.com/bmmmm/mika-birthday/commit/269a16a6d230ed914f5c87f29108f65d70f0721e))
* restore github link in attribution on all pages ([3edfee9](https://github.com/bmmmm/mika-birthday/commit/3edfee92eb329fbf43c068b4ea7089042db4e57e))
* restore UI scale before first paint to stop reload wobble ([d0f7265](https://github.com/bmmmm/mika-birthday/commit/d0f726581504f25b13470b1f4918ad5f31c69b90))
* show correct buttons in upload stage based on file size ([aff911d](https://github.com/bmmmm/mika-birthday/commit/aff911d8c4edd32ecb22bff926fd826b0ba4f06f))
* url tab is default in meme picker, upload moved to second position ([8d0144e](https://github.com/bmmmm/mika-birthday/commit/8d0144eeb5db20cdebc5e3c7ceaf4b728eeb0393))
* validate ranges, token separators, and loader fallbacks ([8f6477f](https://github.com/bmmmm/mika-birthday/commit/8f6477ff52dd9a5f330262a17a6a7324e4f69bd3))

## Changelog
