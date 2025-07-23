---
title: "Specifications"
draft: false
menu:
  docs:
    title:
    parent: "ALPHA-One"
    identifier: "ALPHA-One/Specifications"
    weight: 2
---

## Main Board and SoC Specification

* Based on [StarPro64 Single Board Computer wiki page](/documentation/StarPro64/)
* Based on [ESWIN EIC7700X SoC](https://www.eswincomputing.com/en/products/index/36/10.html)

{{< figure src="/documentation/ALPHA-One/images/EIC7700X_Block_Diagram.png" caption="EIC7700X block diagram" width="800" >}}

## Features

### System Memory

* 32GB 64bits LPDDR5@6400MHz RAM Memory.
* 64GB eMMC preinstalled with 7b Deepseek/Qwen LLM

### Case

* CNC from single Aluminum block
* Passive cooling, built-in heat pipe that directly contact with SoC

### Network

* Dual 10/100/1000 Mbps Ethernet 
* 2.4GHz/5GHz MIMO WiFi 802.11 b/g/n/ac/ax with Bluetooth 5.3

### Expansion Ports

* 2&times; USB3.0 Dedicated Host port
* 2&times; USB2.0 Shared Host port
* Digital Video output up to 4K@60Hz
* 3.5mm audio Jack with mic in

## Certifications

* Not yet available

## Potential Improvement

* Current 7bLLM throughput is around 3.5 tokens/second using docker form, potential improve up to 10 tokens/second  when operates LLM in native mode.
* Potential increase LLM capability from 7b to 15b with system software optimization
* If ALPHA-One proven its potential, consider release ALPHA-Two which can host up to 30b LLM
