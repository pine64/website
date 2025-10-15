---
title: "Software"
draft: false
menu:
  docs:
    title:
    parent: "ALPHA-One"
    identifier: "ALPHA-One/Software"
    weight: 1
---

## Releases

### Production release build 20250627

#### Image for 64GB eMMC module

This build contains 7b QWen2 LLM. To access the web UI, open http://alpha-one.local:8000/

Download:

* [Direct download from PINE64 file server](https://files.pine64.org/os/StarPro64/Alpha-ONE%20image-20250627.img.gz)

File information:

* MD5 (GZip file): `d62eeb1645c7b496a0815c4590f798c7`
* File Size: 18.10 GB

| User | Password |
| ------- | ------- |
| `eswin` | `eswin` |

#### Image for 32GB eMMC module and above

This is the early test build that contains both 7b Deepseek and QWen2 LLM build, OS based on ROCKOS. For larger than 32GB eMMC, please use gpart to extend the file partition.

Download:

* [Direct download from PINE64 file server](https://files.pine64.org/SDK/StarPro64/Alpha-ONE_OS_build_32GB-20250420.img.gz)

File information:

* MD5 (GZip file): `6669a436104e97e2ad90679e06f62d78`
* File Size: 18.21 GB

| User | Password |
| ------- | ------- |
| `eswin` | `eswin` |

#### Usage

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

## SDKs

The SDK documents can be found under https://files.pine64.org/SDK/StarPro64/docs.7z (some are in Chinese).

File information:

* MD5 (7-Zip file): `8ee9b660c336d9979191d212e9826226`
* File Size: 34 MB

SDK Release:

* 20250228: https://files.pine64.org/SDK/StarPro64/EIC7x_AI_Release_20250228.7z (1.932 GB. MD5 checksum of the 7-Zip file is `f9171ec8b30e5d4d8eda1185f72af5e4`.)
* 20250330: https://files.pine64.org/SDK/StarPro64/EIC7x_AI_Release_20250330.7z (1.946 GB. MD5 checksum of the 7-Zip file is `8ddc861755ed26785e67674aad8db87c`.)

LLM and tools release:

* LLM 20250228: https://files.pine64.org/SDK/StarPro64/deepseek&qwen-v0228.7z (722 MB. MD5 checksum of the 7-Zip file is `b8ee72ee6a8912afefac3fa43a18be87`)
* Tools 20250228: https://files.pine64.org/SDK/StarPro64/EIC7x_nn-tools_Release_20250228.7z (6.625 GB. MD5 checksum of the 7-Zip file is `868434b274412e173c3e264118dcb336`)