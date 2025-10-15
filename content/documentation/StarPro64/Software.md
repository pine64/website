---
title: "Software"
draft: false
menu:
  docs:
    title:
    parent: "StarPro64"
    identifier: "StarPro64/Software"
    weight: 1
---

The releases are still in **alpha** state and are only fit for development and testing purposes.

## NuttX

NuttX, an Apache project, is a real-time operating system that prioritizes adherence to standards and maintains a compact size.

Read [StarPro64 EIC7700X RISC-V SBC: Maybe LLM on NPU on NuttX?](https://lupyuen.org/articles/starpro64.html) by *lupyuen*.

## RockOS

RockOS is a customized Debian distribution for the EIC770X by PLCT Lab. 

Download: https://fast-mirror.isrc.ac.cn/rockos/images/generic/latest/

More information on this image SDK can be found at: https://github.com/rockos-riscv.

## ALPHA-One

This is the early test build that contains both 7b Deepseek and QWen2 LLM build, OS based on RockOS. The image for 32 GB eMMC modules and above. For larger than 32GB eMMC, please use gpart to extend the file partition.

Download:

* [Direct download from PINE64 file server](https://files.pine64.org/SDK/StarPro64/Alpha-ONE_OS_build_32GB-20250420.img.gz)

File information:

* MD5 (GZip file): `6669a436104e97e2ad90679e06f62d78`
* File Size: 18.21 GB

| User | Password |
| ------- | ------- |
| `eswin` | `eswin` |

To explore LLM, use terminal program and execute below command lines:

DeepSeek 7b LLM command:

```Shell
$ sudo /opt/eswin/sample-code/npu_sample/qwen_sample/bin/es_qwen2 /opt/eswin/sample-code/npu_sample/qwen_sample/src/deepseek_r1_distill_qwen_7b/config.json
```

Qwen2 7bLLM command:
```Shell
$ sudo /opt/eswin/sample-code/npu_sample/qwen_sample/bin/es_qwen2 /opt/eswin/sample-code/npu_sample/qwen_sample/src/qwen2_7b/config.json
```

Qwen2 0.5bLLM command:
```Shell
$ sudo /opt/eswin/sample-code/npu_sample/qwen_sample/bin/es_qwen2 /opt/eswin/sample-code/npu_sample/qwen_sample/src/qwen2_0_5b/config.json
```

---

## SDKs

SDK document (some in Chinese): https://files.pine64.org/SDK/StarPro64/docs.7z (34 MB. MD5 checksum of the 7-Zip file is `8ee9b660c336d9979191d212e9826226`)

STARPro64 Uboot and Linux Kernel Release:

* 20250330: https://files.pine64.org/SDK/StarPro64/starpro64-sdk-20250330.7z (666 MB. MD5 checksum of the 7-Zip file is `12d44c21a990a64097611ba44eb3c56f`)

### AI SDK Release

* 20250228: https://files.pine64.org/SDK/StarPro64/EIC7x_AI_Release_20250228.7z (1.932 GB. MD5 checksum of the 7-Zip file is `f9171ec8b30e5d4d8eda1185f72af5e4`)
* 20250330: https://files.pine64.org/SDK/StarPro64/EIC7x_AI_Release_20250330.7z (1.946 GB. MD5 checksum of the 7-Zip file is `8ddc861755ed26785e67674aad8db87c`)
* 20250530: https://files.pine64.org/SDK/StarPro64/EIC7x_AI_Release_20250530.7z (1.897 GB. MD5 checksum of the 7-Zip file is `171a147448e42916dd06480f6b129c25`)
* 20250630: https://files.pine64.org/SDK/StarPro64/EIC7x_AI_Release_20250630.7z (1.988 GB. MD5 checksum of the 7-Zip file is `00a91649522cebb94c29fea388c699e4`)
* 20250730: https://files.pine64.org/SDK/StarPro64/EIC7x_AI_Release_20250730.7z (1.839 GB. MD5 checksum of the 7-Zip file is `d0d839dde6b6f4ef8fa509e0fb4848d6`)

### LLM and Neural Network tools release

* LLM 20250228: https://files.pine64.org/SDK/StarPro64/deepseek&qwen-v0228.7z (722 MB. MD5 checksum of the 7-Zip file is `b8ee72ee6a8912afefac3fa43a18be87`)
* NN-Tools 20250228: https://files.pine64.org/SDK/StarPro64/EIC7x_nn-tools_Release_20250228.7z (6.625 GB. MD5 checksum of the 7-Zip file is `868434b274412e173c3e264118dcb336`)
* NN-Tools 20250330: https://files.pine64.org/SDK/StarPro64/EIC7x_nn-tools_Release_20250330.7z (6.625 GB. MD5 checksum of the 7-Zip file is `39348ad2662cc72d12ef411cef2c756c`)
* NN-Tools 20250530: https://files.pine64.org/SDK/StarPro64/EIC7x_nn-tools_Release_20250530.7z (6.625 GB. MD5 checksum of the 7-Zip file is `5c1562cbaaa2772dbad9e0a9dd41c150`)
* NN-Tools 20250630: https://files.pine64.org/SDK/StarPro64/EIC7x_nn-tools_Release_20250630.7z (6.625 GB. MD5 checksum of the 7-Zip file is `dbae3968126c23deed10d5e673aa10ad`)
* NN-Tools 20250730: https://files.pine64.org/SDK/StarPro64/EIC7x_nn-tools_Release_20250730.7z (6.643 GB. MD5 checksum of the 7-Zip file is `e32b6e1ce699fc05105371a7714979a4`)

### Ollama Pack

1. Based on 20250730 Release install whisper and ollama deb package
2. 20250730 path: `/ai_release/EIC7x_AI_Release_20250730`
3. whisper reference: ftp: /share/2025-10-09/whisper/WHISPER_README.md
4. after install ollama deb package，refer to /home/eswin/OLLAMA_README.md for operation manual

Ollma Pack 20251009: https://files.pine64.org/SDK/StarPro64/StarPro64%20Ollam%20Pack%202025-10-09.7z (1.826 GB. MD5 checksum of the 7-Zip file is `ad0093f121963978af41550790643ab4`)