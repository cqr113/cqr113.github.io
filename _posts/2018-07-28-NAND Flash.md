---
layout: post
title:  nand flash的地址问题
date:   2018-07-28 11:00:00 +0800
categories: FLASH
tag: FLASH
---

* content
{:toc}

   读写nand flash时，传给nand flash的地址并不是连续的，即相邻两个page的地址并不连续，前一个page最后一个byte的地址加一并不等于后一个page第一个byte的地址。这是由nand flash的特性决定的，因为nand flash容易出现坏区，需要另外增加spare area来做ECC和保存坏区信息。比如256Mbit nand flash一个page的数据区是512bytes,另外增加16bytes做ECC信息的保存，所以一个page有528bytes.因此，nand flash的地址分为两部分，一个是colume address用来定位一个page内的数据。一个是row address用来索引某个page.

   nor flash的读写地址是连续的，即任何两个相邻数据的地址差是1.

   nand flash的编程和擦除速度比nor flash要快。





