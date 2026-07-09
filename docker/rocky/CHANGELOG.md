# Changelog

## [21.1.8](https://github.com/snowdreamtech/llvm/compare/rocky-v21.1.8...rocky-v21.1.8) (2026-07-09)


### 🐛 Bug Fixes

* use ghcr.io for base images to avoid rate limits ([9f1d73a](https://github.com/snowdreamtech/llvm/commit/9f1d73a75a61f2f368f5572c4bd28f4c92ef8fd5))


### ♻️ Miscellaneous Chores

* add 0-git-keep.sh to prevent empty entrypoint.d directories ([ce77247](https://github.com/snowdreamtech/llvm/commit/ce77247762becc1edf85ec7b57747d3f3127044a))
* merge commit '099e99cb9e0a5dc0738f38403b3c025b0225f914' into dev ([0f9ca71](https://github.com/snowdreamtech/llvm/commit/0f9ca71aa7483261e25efb5f6f5047abd0d0519c))
* release main ([4011a21](https://github.com/snowdreamtech/llvm/commit/4011a21a23395acc9545168c95ca0ec5c867e7d3))
* release main ([d52be5c](https://github.com/snowdreamtech/llvm/commit/d52be5cf0c5cff45f7f72e973d62c94b48855e1b))
* release main ([f66597a](https://github.com/snowdreamtech/llvm/commit/f66597a5feae95e8853f4cc730c81e93e172f6ca))
* release main ([b3a5cc9](https://github.com/snowdreamtech/llvm/commit/b3a5cc9ef0a64a7bc04ed7c2acf0cca5327c5c26))
* **release:** deduplicate CHANGELOG headers ([4f07b71](https://github.com/snowdreamtech/llvm/commit/4f07b71194f58ba214f1fb60ce0dc56d71c499e2))
* **release:** deduplicate CHANGELOG headers ([3068d88](https://github.com/snowdreamtech/llvm/commit/3068d883bc6167773d046d3b2b0e4c479e4fee39))
* **release:** deduplicate CHANGELOG headers ([82be3d5](https://github.com/snowdreamtech/llvm/commit/82be3d5576b65b7f69b1a9afb8604f2c8f0e47f7))
* **speckit:** manual auto-commit trigger ([5f8a5a9](https://github.com/snowdreamtech/llvm/commit/5f8a5a9cba5d6bd42a65eaabfecd6e18b01aeeb0))

## [21.1.8](https://github.com/snowdreamtech/llvm/compare/rocky-v21.1.8...rocky-v21.1.8) (2026-06-21)


### 🐛 Bug Fixes

* ensure cross-platform compatibility by conditionally installing arch-specific packages ([45029f2](https://github.com/snowdreamtech/llvm/commit/45029f26527e3f9bca372ac3aba3305d1d21fd1d))
* remove epel-release and crb which fail on Rocky 10 ([6cc63be](https://github.com/snowdreamtech/llvm/commit/6cc63bef25f0a9f1d255bba851b1c559397f06b9))
* unconditionally skip missing llvm peripheral sub-packages across platforms ([c150dc2](https://github.com/snowdreamtech/llvm/commit/c150dc259e39a622042099670391f875af820777))


### 🛠 Refactoring

* **docker:** align Dockerfiles with base image structure ([232574f](https://github.com/snowdreamtech/llvm/commit/232574fed8418f8c7f257d001e951361dfa467a0))
* remove redundant docker-entrypoint.sh files ([87c576b](https://github.com/snowdreamtech/llvm/commit/87c576b27731ad11c5bc0ebc661e07c5a09ff1c1))
* reorganize distribution variants into docker directory ([67a8c91](https://github.com/snowdreamtech/llvm/commit/67a8c911e21801bf12b3e83d02e22f3b3f59a2ba))


### 📖 Documentation

* add detailed comments to entrypoint initialization scripts ([f42cbaa](https://github.com/snowdreamtech/llvm/commit/f42cbaab6edfbc5c38c2a636dfd8651fea900940))


### ♻️ Miscellaneous Chores

* clear previous changelog entries ([1a3bb6d](https://github.com/snowdreamtech/llvm/commit/1a3bb6df626081f796d3d3fa410e98f11fc383e3))
* **deps:** bump base images to alpine 3.24.0, debian 13.5.0, rocky 10.2.0 ([1688969](https://github.com/snowdreamtech/llvm/commit/168896956d2f4c7f91309c4c98ffef36ca7e8546))
* release main ([deb8454](https://github.com/snowdreamtech/llvm/commit/deb8454df7518d56939ab3851245a4cd7b03d709))
* release main ([d87cb81](https://github.com/snowdreamtech/llvm/commit/d87cb815685ad9b5b43d4b9a195c68dee2fd8065))
* release main ([78328d2](https://github.com/snowdreamtech/llvm/commit/78328d20bd3697d48ea90aee8d0eaa6af4ccc09c))
* release main ([b720ad5](https://github.com/snowdreamtech/llvm/commit/b720ad57dd1691d8ae07dcac7d46d0bd257af3a0))
* release main ([32dd84d](https://github.com/snowdreamtech/llvm/commit/32dd84de4be973395d0867b5d527d528948a35df))
* release main ([725c69f](https://github.com/snowdreamtech/llvm/commit/725c69fdcc222b5b83d0690629ce213a68c586ab))
* release main ([070b694](https://github.com/snowdreamtech/llvm/commit/070b694a702763b60fc6b057a81418320418cafa))
* release main ([36d1211](https://github.com/snowdreamtech/llvm/commit/36d1211036847a8c6aaa01a21a1c695a47b71d45))
* release main ([9ad4f94](https://github.com/snowdreamtech/llvm/commit/9ad4f9490832efdc310f2ebbd8c77f3404daf07f))
* release main ([b0684a3](https://github.com/snowdreamtech/llvm/commit/b0684a32a652e83506451e6056168cfec8b9142c))
* release main ([495e18a](https://github.com/snowdreamtech/llvm/commit/495e18a4babcb06a12c2f5aec9ea571d97cb32e3))
* release main ([d4a3a34](https://github.com/snowdreamtech/llvm/commit/d4a3a34b00a6b9f381cd5d556749c257516b2f08))
* release main ([28d9426](https://github.com/snowdreamtech/llvm/commit/28d94263f4374017274707faef7183917b689be9))
* **release:** deduplicate CHANGELOG headers ([d47fb44](https://github.com/snowdreamtech/llvm/commit/d47fb44cb105b368722d7d0e210a27b525f82d87))
* **release:** deduplicate CHANGELOG headers ([e795177](https://github.com/snowdreamtech/llvm/commit/e79517795d98b9f8292ef956586a6dc03932d03c))
* **release:** deduplicate CHANGELOG headers ([27919e4](https://github.com/snowdreamtech/llvm/commit/27919e4baf4aab5b2a2bf32a7d437b05a717c11b))
* **release:** deduplicate CHANGELOG headers ([438190d](https://github.com/snowdreamtech/llvm/commit/438190d297c151c75eca4912fdc22c285d5ec1ea))
* **release:** deduplicate CHANGELOG headers ([256f043](https://github.com/snowdreamtech/llvm/commit/256f04311b2344f2648ca5bcf407146f8c690258))
* **release:** deduplicate CHANGELOG headers ([d263aae](https://github.com/snowdreamtech/llvm/commit/d263aae7b223103a01dd0e114430381c5d863dd7))
* **release:** deduplicate CHANGELOG headers ([133954e](https://github.com/snowdreamtech/llvm/commit/133954e95cfae85cbba2fb9c1ac5acbc677ca39d))
* **release:** deduplicate CHANGELOG headers ([1d82410](https://github.com/snowdreamtech/llvm/commit/1d82410d6038be22d7741f1519826f30023b0f3e))
* **release:** deduplicate CHANGELOG headers ([5e1a539](https://github.com/snowdreamtech/llvm/commit/5e1a5390319933b48d20ad993714587d826c0aa7))
* **release:** fix release-please component versions and align dockerfiles ([505ca4f](https://github.com/snowdreamtech/llvm/commit/505ca4f4a9b0d91263ef4cfb26eba228c6cb4c38))
* **release:** implement automatic changelog deduplication step ([282c220](https://github.com/snowdreamtech/llvm/commit/282c22081e1ad7a1a010a7f297d20bc7c9b416a7))
