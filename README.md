# Awesome OFD [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> 精选的 OFD（开放版式文档，[GB/T 33190-2016](https://openstd.samr.gov.cn/bzgk/gb/newGbInfo?hcno=33D6DA6D2B5EDB896F4A2B75D22C4970)）库、工具与资源列表。

OFD 是中国的电子文件版式标准，广泛用于电子发票、电子证照、电子档案。生态以 Java（ofdrw）、Go、JavaScript 为主，其余语言多为个人项目。

本列表按语言分门别类，并用统一维度标注各库的能力，方便横向对比后按需选型。

## Contents

- [图例](#图例)
- [规范与文档](#规范与文档)
- [Go](#go)
- [Rust](#rust)
- [Python](#python)
- [Java](#java)
- [C++](#c)
- [.NET](#net)
- [JavaScript](#javascript)
- [Pascal](#pascal)
- [选型参考（可能过时）](#选型参考可能过时)
- [贡献](#贡献)
- [说明](#说明)

## 图例

能力列的含义：

| 列 | 含义 |
|----|------|
| **许可证** | 项目的开源许可证 |
| **预览** | 内置 OFD 预览/显示能力（查看器、浏览器渲染或可视化组件） |
| **解析** | 解析 OFD 文档结构与内容 |
| **发票** | 支持电子发票类 OFD 处理（发票解析/信息提取、验签验章、发票渲染等） |
| **→ 图片 / → PDF / → TXT / → SVG / → Md / → HTML** | 导出目标格式的能力 |
| **PDF → OFD** | 支持 PDF 转 OFD 导入 |
| **生成** | 以代码方式生成/创建 OFD 文档 |
| **签章** | 电子签名/盖章（签名、验签、印章） |
| **加密文档** | OFD 文档级加密/解密（GM/T 0099-2020，口令或证书加密、解密打开） |
| **打印** | 内置 OFD 打印能力（系统打印管线/对话框，或按页渲染后打印） |
| **检索** | 文档内全文检索/关键词定位（含跨对象文字搜索、命中跳页） |
| **注释** | OFD 注释对象（Annots）的读取、渲染或写入 |
| **归档** | 长期归档能力（归档预检、清单或封装准备，如 GB/T 33190、GB/T 42133） |
| **修改** | 程序化修改已有 OFD 文档内容（区别于「编辑器」的交互式编辑） |
| **编辑器** | 附带可视化编辑界面（GUI/WYSIWYG，可交互增删改文档内容） |

标记说明：

- ✅ 支持
- ⚠️ 部分支持 / 有条件限制（⚠️ 的具体含义见各列下方注释）
- ❌ 不支持

部分列的 ⚠️ 含义：

- **发票 ⚠️**：可兼容发票文档的通用 OFD 库，但无发票专项功能。
- **→ HTML ⚠️**：在浏览器中基于 Canvas 渲染显示，但不直接生成 HTML DOM/SVG 结构。
- **PDF → OFD ⚠️**：仅支持部分内容（仅文本/图片），或对非嵌入字体等常见 PDF 直接失败。
- **加密文档 ⚠️**：仅支持部分加解密能力，例如支持加密但不支持解密打开。

## 规范与文档

- [GB/T 33190-2016 电子文件存储与交换格式 版式文档](https://openstd.samr.gov.cn/bzgk/gb/newGbInfo?hcno=33D6DA6D2B5EDB896F4A2B75D22C4970) — OFD 国家标准正文
- [ofd-benchmark/docs/ofd-libraries.md](https://github.com/zc310/ofd-benchmark) — 各语言 OFD 库的能力对比与基准测试来源

## Go

- [go-zc310](https://github.com/zc310/ofd) - 能力覆盖最广（预览、发票、PDF→OFD、签章、SVG/MD/HTML 导出）
- [go-ofd](https://github.com/ppxz2014/go-ofd) - OFD 解析与签章的轻量库
- [go-ofdgo](https://github.com/xiaoqidun/ofdgo) - 全能库，唯一自带可视化编辑器，PDF→OFD 实测成功率最高
- [leijacob-ofd](https://gitee.com/leijacob/ofd) - 支持解析、PDF→OFD、生成、签章与修改
- [ofd-go](https://github.com/itlabers/ofd-go) - 轻量解析 + 签章
- [pdf-to-ofd](https://github.com/huanxiang666/pdf-to-ofd) - 图片型 PDF→OFD 转换（对常见 PDF 常失败）
- [signer-tools](https://gitee.com/leijacob/signer-tools) - OFD 签名/盖章工具集

**能力矩阵**

|                            库                            |   许可证   | 预览 | 解析 | 发票 | → 图片 | → PDF | → TXT | → SVG | → Md | → HTML | PDF → OFD | 生成 | 签章 | 加密文档 | 打印 | 检索 | 注释 | 归档 | 修改 | 编辑器 |
|:--------------------------------------------------------:|:----------:|:----:|:----:|:----:|:------:|:-----:|:-----:|:-----:|:----:|:------:|:---------:|:----:|:----:|:--------:|:----:|:----:|:----:|:----:|:----:|:------:|
|         [go-zc310](https://github.com/zc310/ofd)         | Apache-2.0 |  ✅  |  ✅  |  ✅  |   ✅   |  ✅   |  ✅   |  ✅   |  ✅  |   ✅   |    ✅     |  ✅  |  ✅  |    ✅    |  ❌  |  ✅  |  ❌  |  ✅  |  ✅  |   ❌   |
|      [go-ofdgo](https://github.com/xiaoqidun/ofdgo)      | Apache-2.0 |  ✅  |  ✅  |  ✅  |   ✅   |  ✅   |  ✅   |  ✅   |  ❌  |   ❌   |    ✅     |  ✅  |  ✅  |    ❌    |  ❌  |  ✅  |  ❌  |  ❌  |  ✅  |   ✅   |
|       [ofd-go](https://github.com/itlabers/ofd-go)       | Apache-2.0 |  ❌  |  ✅  |  ⚠️  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ✅  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|       [go-ofd](https://github.com/ppxz2014/go-ofd)       | Apache-2.0 |  ❌  |  ✅  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ✅  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|      [leijacob-ofd](https://gitee.com/leijacob/ofd)      |     无     |  ❌  |  ✅  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ✅     |  ✅  |  ✅  |    ❌    |  ❌  |  ❌  |  ⚠️  |  ❌  |  ✅  |   ❌   |
| [signer-tools](https://gitee.com/leijacob/signer-tools)  |     无     |  ❌  |  ✅  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ✅  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
| [pdf-to-ofd](https://github.com/huanxiang666/pdf-to-ofd) |    MIT     |  ❌  |  ❌  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ⚠️     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |

## Rust

- [OFD Reader](http://123.57.45.115/) - 高速、流畅、精准、深入符合国家标准 GB/T 33190 的 OFD 版式文档阅读器
- [easyofd-rust](https://github.com/easy-4-rust/easyofd-rust) - 文档最完整的 Rust OFD 库，适合生成、签章、PDF/MD 导出
- [easy_print](https://github.com/qzue/easy_print) - 发票打印工具，自研 OFD→PDF（矢量渲染 + 印章烘焙）
- [fapiao-print](https://github.com/erma0/fapiao-print) - 发票 OFD 预览与打印，支持 PDF/SVG 导出
- [jian-yue](https://github.com/lapin2024/jian-yue) - Rust 阅读器，预览 + 编辑器 + 文本提取，PDF→OFD/签章/修改为部分支持
- [linuxdeepin-rofd](https://github.com/linuxdeepin/rofd) - 解析 + 渲染 + 图片导出（LGPL-2.1）
- [ofdbox-rust](https://github.com/ofdbox/ofdbox) - Rust 工具箱，支持 OFD↔PDF/PNG 转换与 GM/T 0099 签章验签
- [ofd-rs](https://github.com/YeaLooooo/ofd-rs) - 图片转 OFD 的生成器
- [ofd-utility](https://github.com/ofd-utility/ofd-utility) - 解析、图片导出与验签
- [ofd-viewer](https://github.com/shaoyi1998/ofd-viewer) - 查看器，支持 PDF/TXT 导出
- [ofdmanager](https://github.com/feuvan/ofdmanager) - 渲染与图片导出
- [ofdsdk](https://github.com/KaiserY/ofdsdk) - 基础解析 SDK
- [rofd](https://github.com/office-rs/rofd) - 渲染与文档修改
- [rs_ofd](https://github.com/geniusnut/rs_ofd) - 解析与图片导出
- [SteleOFD](https://github.com/emfox/SteleOFD) - 解析 / 验签 / 修改引擎，项目早期阶段

**能力矩阵**

|                             库                              |   许可证   | 预览 | 解析 | 发票 | → 图片 | → PDF | → TXT | → SVG | → Md | → HTML | PDF → OFD | 生成 | 签章 | 加密文档 | 打印 | 检索 | 注释 | 归档 | 修改 | 编辑器 |
|:-----------------------------------------------------------:|:----------:|:----:|:----:|:----:|:------:|:-----:|:-----:|:-----:|:----:|:------:|:---------:|:----:|:----:|:--------:|:----:|:----:|:----:|:----:|:----:|:------:|
| [easyofd-rust](https://github.com/easy-4-rust/easyofd-rust) | Apache-2.0 |  ❌  |  ✅  |  ⚠️  |   ✅   |  ✅   |  ❌   |  ❌   |  ✅  |   ❌   |    ⚠️     |  ✅  |  ✅  |    ✅    |  ❌  |  ✅  |  ❌  |  ✅  |  ✅  |   ❌   |
|     [ofdmanager](https://github.com/feuvan/ofdmanager)      |    MIT     |  ✅  |  ✅  |  ❌  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ⚠️  |  ❌  |  ❌  |   ❌   |
|        [rs_ofd](https://github.com/geniusnut/rs_ofd)        |    MIT     |  ❌  |  ✅  |  ❌  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|  [ofd-utility](https://github.com/ofd-utility/ofd-utility)  |    MIT     |  ❌  |  ✅  |  ❌  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ✅  |    ❌    |  ❌  |  ❌  |  ✅  |  ❌  |  ❌  |   ❌   |
|       [ofdbox-rust](https://github.com/ofdbox/ofdbox)       | Apache-2.0 |  ❌  |  ✅  |  ❌  |   ✅   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ⚠️     |  ❌  |  ✅  |    ✅    |  ❌  |  ❌  |  ✅  |  ❌  |  ✅  |   ❌   |
|         [ofdsdk](https://github.com/KaiserY/ofdsdk)         | Apache-2.0 |  ❌  |  ✅  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|          [rofd](https://github.com/office-rs/rofd)          | Apache-2.0 |  ✅  |  ✅  |  ❌  |   ⚠️   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ✅  |  ✅  |  ❌  |  ✅  |   ❌   |
|   [ofd-viewer](https://github.com/shaoyi1998/ofd-viewer)    |    MIT     |  ✅  |  ✅  |  ❌  |   ❌   |  ✅   |  ✅   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ✅  |  ✅  |  ✅  |  ❌  |  ❌  |   ❌   |
|    [fapiao-print](https://github.com/erma0/fapiao-print)    |    MIT     |  ✅  |  ✅  |  ✅  |   ⚠️   |  ✅   |  ❌   |  ✅   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|      [jian-yue](https://github.com/lapin2024/jian-yue)      |    MIT     |  ✅  |  ✅  |  ⚠️  |   ✅   |  ⚠️   |  ✅   |  ❌   |  ❌  |   ❌   |    ⚠️     |  ❌  |  ⚠️  |    ❌    |  ✅  |  ✅  |  ✅  |  ❌  |  ⚠️  |   ✅   |
|   [linuxdeepin-rofd](https://github.com/linuxdeepin/rofd)   |  LGPL-2.1  |  ✅  |  ✅  |  ⚠️  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|      [easy_print](https://github.com/qzue/easy_print)       |    MIT     |  ✅  |  ✅  |  ✅  |   ❌   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ✅  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|        [ofd-rs](https://github.com/YeaLooooo/ofd-rs)        | Apache-2.0 |  ❌  |  ❌  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ✅  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|        [SteleOFD](https://github.com/emfox/SteleOFD)        | Apache-2.0 |  ✅  |  ✅  |  ⚠️  |   ✅   |  ✅   |  ❌   |  ✅   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ✅  |    ❌    |  ✅  |  ✅  |  ✅  |  ✅  |  ✅  |   ❌   |

## Python

- [easyofd](https://pypi.org/project/easyofd/) - 发票 OFD 渲染与预览，支持 PDF→OFD
- [fapiao-ofd2pdf](https://github.com/seawander/fapiao-ofd2pdf) - 发票 OFD 转 PDF
- [ofd-parser](https://github.com/jyh2012/ofd-parser) - 解析与预览
- [ofd2img](https://pypi.org/project/ofd2img/) - OFD 转图片
- [ofd2pdf](https://github.com/jsyzdej/ofd2pdf) - 基于图片渲染转 PDF（无可提取文本）
- [ofdreader](https://pypi.org/project/ofdreader/) - 解析 + 生成 + PDF/TXT 导出，适合文本提取
- [OFDtoPDF](https://github.com/njuzzy1979/OFDtoPDF) - 轻量 OFD→PDF
- [OfficeMaster](https://github.com/Chingliu/OfficeMaster_document_convert_system) - 办公文档转换系统，支持生成与 PDF→OFD
- [pdf2ofd](https://github.com/wanglrebe/pdf2ofd) - 专注 PDF→OFD 导入
- [swingmonkey-ofd2pdf](https://github.com/swingmonkey/ofd2pdf) - 发票 OFD→PDF 转换，支持可插拔后端
- [ofdkit](https://github.com/Edgar-311/ofdkit) - Python 标准库发票工具，支持文本提取、发票字段 JSON 与批量 CSV 查重
- [ce-conversion-engine](https://github.com/ThePandaQ/ce-conversion-engine) - 文档转换引擎，支持 OFD/PDF 转换、文本提取与生成（AGPL-3.0）
- [ofd-to-pdf (campfire)](https://github.com/campfire-code/ofd-to-pdf) - Python 发票 OFD→PDF 转换
- [win-doc-converter](https://github.com/yefd/win-doc-converter) - 数科/WPS DLL 封装的 OFD→PDF（Windows）

**能力矩阵**

|                                        库                                        |   许可证   | 预览 | 解析 | 发票 | → 图片 | → PDF | → TXT | → SVG | → Md | → HTML | PDF → OFD | 生成 | 签章 | 加密文档 | 打印 | 检索 | 注释 | 归档 | 修改 | 编辑器 |
|:--------------------------------------------------------------------------------:|:----------:|:----:|:----:|:----:|:------:|:-----:|:-----:|:-----:|:----:|:------:|:---------:|:----:|:----:|:--------:|:----:|:----:|:----:|:----:|:----:|:------:|
|                   [easyofd](https://pypi.org/project/easyofd/)                   | Apache-2.0 |  ✅  |  ✅  |  ✅  |   ✅   |  ⚠️   |  ❌   |  ❌   |  ❌  |   ❌   |    ✅     |  ✅  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|          [fapiao-ofd2pdf](https://github.com/seawander/fapiao-ofd2pdf)           |    MIT     |  ❌  |  ✅  |  ⚠️  |   ❌   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ✅  |  ❌  |  ❌  |   ❌   |
|                   [ofd2img](https://pypi.org/project/ofd2img/)                   | Apache-2.0 |  ❌  |  ✅  |  ⚠️  |   ✅   |  ⚠️   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                  [ofd2pdf](https://github.com/jsyzdej/ofd2pdf)                   |     无     |  ❌  |  ✅  |  ❌  |   ✅   |  ⚠️   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ✅  |  ❌  |  ❌  |   ❌   |
|                [OFDtoPDF](https://github.com/njuzzy1979/OFDtoPDF)                |     无     |  ❌  |  ✅  |  ❌  |   ❌   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ⚠️  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                 [ofdreader](https://pypi.org/project/ofdreader/)                 |    MIT     |  ❌  |  ✅  |  ❌  |   ❌   |  ✅   |  ✅   |  ❌   |  ❌  |   ❌   |    ❌     |  ✅  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                 [pdf2ofd](https://github.com/wanglrebe/pdf2ofd)                  |    MIT     |  ❌  |  ❌  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ✅     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|               [ofd-parser](https://github.com/jyh2012/ofd-parser)                |     无     |  ✅  |  ✅  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
| [OfficeMaster](https://github.com/Chingliu/OfficeMaster_document_convert_system) |    MIT     |  ❌  |  ✅  |  ❌  |   ❌   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ✅     |  ✅  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|          [swingmonkey-ofd2pdf](https://github.com/swingmonkey/ofd2pdf)           |    MIT     |  ❌  |  ✅  |  ⚠️  |   ❌   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|          [win-doc-converter](https://github.com/yefd/win-doc-converter)          |     无     |  ❌  |  ✅  |  ⚠️  |   ❌   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|    [ce-conversion-engine](https://github.com/ThePandaQ/ce-conversion-engine)     |  AGPL-3.0  |  ❌  |  ✅  |  ⚠️  |   ✅   |  ⚠️   |  ✅   |  ❌   |  ❌  |   ❌   |    ✅     |  ✅  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                  [ofdkit](https://github.com/Edgar-311/ofdkit)                   | Apache-2.0 |  ❌  |  ✅  |  ✅  |   ❌   |  ❌   |  ✅   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |

## Java

- [easyofd-java](https://github.com/11627685/easyofd-java) - 生成与签章
- [fuyue-convert](https://github.com/wmforever/fuyue-convert) - 文档转换工具箱（图片/PDF/TXT 导出、签章）
- [JIMU-ConvertPreview](https://github.com/zhangzhen1979/JIMU-ConvertPreview) - 积木报表预览插件，支持生成与 PDF→OFD
- [kkFileView](https://github.com/kekingcn/kkFileView) - 在线文件预览服务（含发票 OFD）
- [kkfileviewxg](https://github.com/gaoxingzaq/kkfileviewxg) - kkFileView 的 OFD/SVG 支持分支
- [ofd-analyze](https://github.com/cooker/ofd-analyze) - 发票解析与识别
- [ofd-parser-tika](https://github.com/ryecrow/ofd-parser) - Apache Tika 解析插件，用于全文检索
- [ofd-server](https://github.com/maczh/ofd-server) - OFD 处理服务（PDF→OFD、生成、签章、修改）
- [ofdToPdf](https://github.com/thebigboy/ofdToPdf) - OFD→PDF
- [DocPaw-OFDH](https://github.com/bushizhuan/DocPaw-OFDH) - 医疗 OFD-H 生成与校验，支持 PDF→OFD、SM2 签章封装和元数据写入
- [ofdbox](https://gitee.com/bookhhu/ofdbox) - 解析与图片导出
- [ofdbox-viewer](https://github.com/jiayao-zhang/ofdbox-viewer) - 浏览器端 OFD 预览
- [ofdrw](https://github.com/ofdrw/ofdrw) - Java 生态事实标准，能力覆盖最全

**能力矩阵**

|                                     库                                      |   许可证   | 预览 | 解析 | 发票 | → 图片 | → PDF | → TXT | → SVG | → Md | → HTML | PDF → OFD | 生成 | 签章 | 加密文档 | 打印 | 检索 | 注释 | 归档 | 修改 | 编辑器 |
|:---------------------------------------------------------------------------:|:----------:|:----:|:----:|:----:|:------:|:-----:|:-----:|:-----:|:----:|:------:|:---------:|:----:|:----:|:--------:|:----:|:----:|:----:|:----:|:----:|:------:|
|                   [ofdrw](https://github.com/ofdrw/ofdrw)                   | Apache-2.0 |  ❌  |  ✅  |  ✅  |   ✅   |  ✅   |  ✅   |  ✅   |  ❌  |   ✅   |    ✅     |  ✅  |  ✅  |    ✅    |  ❌  |  ❌  |  ✅  |  ✅  |  ✅  |   ❌   |
|          [easyofd-java](https://github.com/11627685/easyofd-java)           | Apache-2.0 |  ❌  |  ✅  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ✅  |  ✅  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                 [ofdbox](https://gitee.com/bookhhu/ofdbox)                  | Apache-2.0 |  ❌  |  ✅  |  ❌  |   ✅   |  ⚠️   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ✅  |  ❌  |  ❌  |   ❌   |
|            [ofd-analyze](https://github.com/cooker/ofd-analyze)             |     无     |  ⚠️  |  ✅  |  ✅  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|              [ofdToPdf](https://github.com/thebigboy/ofdToPdf)              |     无     |  ❌  |  ✅  |  ❌  |   ❌   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
| [JIMU-ConvertPreview](https://github.com/zhangzhen1979/JIMU-ConvertPreview) | Apache-2.0 |  ✅  |  ✅  |  ❌  |   ✅   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ✅     |  ✅  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ⚠️  |   ❌   |
|       [ofdbox-viewer](https://github.com/jiayao-zhang/ofdbox-viewer)        |     无     |  ✅  |  ✅  |  ❌  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|            [kkFileView](https://github.com/kekingcn/kkFileView)             |     无     |  ✅  |  ✅  |  ✅  |   ✅   |  ⚠️   |  ❌   |  ❌   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ❌  |    ❌    |  ⚠️  |  ❌  |  ❌  |  ❌  |  ⚠️  |   ❌   |
|         [kkfileviewxg](https://github.com/gaoxingzaq/kkfileviewxg)          |     无     |  ✅  |  ✅  |  ❌  |   ✅   |  ✅   |  ❌   |  ✅   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ❌  |    ❌    |  ⚠️  |  ❌  |  ❌  |  ❌  |  ⚠️  |   ❌   |
|              [ofd-server](https://github.com/maczh/ofd-server)              |     无     |  ❌  |  ❌  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ✅     |  ✅  |  ✅  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ✅  |   ❌   |
|          [ofd-parser-tika](https://github.com/ryecrow/ofd-parser)           | Apache-2.0 |  ❌  |  ✅  |  ❌  |   ❌   |  ❌   |  ✅   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|         [fuyue-convert](https://github.com/wmforever/fuyue-convert)         | Apache-2.0 |  ❌  |  ✅  |  ⚠️  |   ✅   |  ✅   |  ✅   |  ❌   |  ❌  |   ❌   |    ⚠️     |  ❌  |  ⚠️  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|          [DocPaw-OFDH](https://github.com/bushizhuan/DocPaw-OFDH)           | Apache-2.0 |  ❌  |  ✅  |  ⚠️  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ⚠️     |  ✅  |  ✅  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ✅  |   ❌   |

## C++

- [docwriter](https://github.com/isee15/docwriter) - 仅做 OFD 生成
- [libofd](https://github.com/uukuguy/libofd) - 解析、生成、PDF→OFD 与修改
- [ofdEditor](https://github.com/mcoder2014/ofdEditor) - Qt 桌面查看器/编辑器，支持生成
- [OFDEditor](https://github.com/KikyoShaw/OFDEditor) - Qt 桌面编辑器，支持生成与修改
- [ofdpdfsigner](https://github.com/fanzizheng/ofdpdfsigner) - 签名验签，支持 PDF/SVG 导出与 PDF→OFD
- [ofdReader](https://github.com/Micats/ofdReader) - 渲染与图片导出，部分签章支持
- [OfdiumEx](https://github.com/roy19831015/OfdiumEx) - 渲染与图片导出
- [papers-ofd](https://github.com/YangtseSu/papers-ofd) - GNOME Papers 的 OFD 后端（rofd C ABI），打印即 PDF
- [XilouReader](https://github.com/Chingliu/XilouReader) - 一体化方案：预览 + 发票 + 生成 + 签章 + PDF→OFD
- [xilou_core](https://github.com/Chingliu/xilou_core) - ofdReader 系核心库，渲染与图片导出
- [ZipViewer](https://github.com/CryFeiFei/ZipViewer) - 轻量查看器

**能力矩阵**

|                             库                             |    许可证    | 预览 | 解析 | 发票 | → 图片 | → PDF | → TXT | → SVG | → Md | → HTML | PDF → OFD | 生成 | 签章 | 加密文档 | 打印 | 检索 | 注释 | 归档 | 修改 | 编辑器 |
|:----------------------------------------------------------:|:------------:|:----:|:----:|:----:|:------:|:-----:|:-----:|:-----:|:----:|:------:|:---------:|:----:|:----:|:--------:|:----:|:----:|:----:|:----:|:----:|:------:|
| [ofdpdfsigner](https://github.com/fanzizheng/ofdpdfsigner) |   BSL-1.1    |  ✅  |  ✅  |  ❌  |   ✅   |  ✅   |  ❌   |  ✅   |  ❌  |   ❌   |    ✅     |  ❌  |  ✅  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|      [ofdReader](https://github.com/Micats/ofdReader)      |      无      |  ✅  |  ✅  |  ❌  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ⚠️  |    ❌    |  ❌  |  ❌  |  ✅  |  ❌  |  ❌  |   ❌   |
|   [XilouReader](https://github.com/Chingliu/XilouReader)   | BSD-3-Clause |  ✅  |  ✅  |  ✅  |   ✅   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ✅     |  ✅  |  ✅  |    ❌    |  ❌  |  ❌  |  ✅  |  ❌  |  ✅  |   ❌   |
|    [xilou_core](https://github.com/Chingliu/xilou_core)    | BSD-3-Clause |  ✅  |  ✅  |  ⚠️  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|      [docwriter](https://github.com/isee15/docwriter)      |     MIT      |  ❌  |  ❌  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ✅  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|        [libofd](https://github.com/uukuguy/libofd)         |     MIT      |  ✅  |  ✅  |  ❌  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ✅     |  ✅  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ✅  |   ❌   |
|    [OFDEditor](https://github.com/KikyoShaw/OFDEditor)     |  Apache-2.0  |  ✅  |  ✅  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ✅  |  ❌  |    ❌    |  ✅  |  ❌  |  ❌  |  ❌  |  ✅  |   ✅   |
|    [OfdiumEx](https://github.com/roy19831015/OfdiumEx)     |  Apache-2.0  |  ✅  |  ✅  |  ❌  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|    [ofdEditor](https://github.com/mcoder2014/ofdEditor)    |     MIT      |  ✅  |  ✅  |  ❌  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ✅  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ✅  |   ✅   |
|    [ZipViewer](https://github.com/CryFeiFei/ZipViewer)     |     MIT      |  ✅  |  ✅  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|   [papers-ofd](https://github.com/YangtseSu/papers-ofd)    |   GPL-2.0    |  ✅  |  ✅  |  ⚠️  |   ✅   |  ✅   |  ✅   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ✅  |  ✅  |  ❌  |  ❌  |  ❌  |   ❌   |

## .NET

- [BootstrapBlazor.OfdReader](https://github.com/BootstrapBlazor/BootstrapBlazor.OfdReader) - 嵌入 Blazor 项目的 OFD 预览控件
- [OFDConverter](https://github.com/wukonggo/OFDConverter) - 专注 PDF→OFD 导入
- [Ofd2Pdf](https://github.com/taurusxin/Ofd2Pdf) - OFD→PDF
- [ofd2pdf](https://github.com/lanbo0829/ofd2pdf) - OFD→PDF
- [OfdViewer](https://github.com/LvYueMing/OfdViewer) - 查看器，支持生成，部分签章支持
- [ofdparser](https://github.com/wangyi160/ofdparser) - 基础解析
- [ofdrw-net](https://github.com/lllooollpp/ofdrw-net) - ofdrw.net 的无许可证分支，签章支持完整
- [ofdrw.net](https://github.com/whynpc9/ofdrw.net) - .NET 版 ofdrw，能力最全（多格式导出 + 生成 + PDF→OFD + 修改）
- [XiaoFeng.Ofd](https://github.com/zhuovi/XiaoFeng.Ofd) - 生成与签章

**能力矩阵**

|                                            库                                             |   许可证   | 预览 | 解析 | 发票 | → 图片 | → PDF | → TXT | → SVG | → Md | → HTML | PDF → OFD | 生成 | 签章 | 加密文档 | 打印 | 检索 | 注释 | 归档 | 修改 | 编辑器 |
|:-----------------------------------------------------------------------------------------:|:----------:|:----:|:----:|:----:|:------:|:-----:|:-----:|:-----:|:----:|:------:|:---------:|:----:|:----:|:--------:|:----:|:----:|:----:|:----:|:----:|:------:|
|                  [XiaoFeng.Ofd](https://github.com/zhuovi/XiaoFeng.Ofd)                   |    MIT     |  ❌  |  ✅  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ✅  |  ✅  |    ❌    |  ❌  |  ❌  |  ✅  |  ❌  |  ❌  |   ❌   |
|                    [OfdViewer](https://github.com/LvYueMing/OfdViewer)                    |    MIT     |  ✅  |  ✅  |  ❌  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ✅  |  ⚠️  |    ❌    |  ❌  |  ❌  |  ✅  |  ❌  |  ❌  |   ❌   |
|                     [ofdrw.net](https://github.com/whynpc9/ofdrw.net)                     |    MIT     |  ❌  |  ✅  |  ❌  |   ✅   |  ✅   |  ✅   |  ✅   |  ❌  |   ✅   |    ✅     |  ✅  |  ⚠️  |    ✅    |  ❌  |  ❌  |  ✅  |  ✅  |  ✅  |   ❌   |
|                   [ofdrw-net](https://github.com/lllooollpp/ofdrw-net)                    |     无     |  ❌  |  ✅  |  ❌  |   ✅   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ✅     |  ✅  |  ✅  |    ✅    |  ❌  |  ❌  |  ✅  |  ❌  |  ❌  |   ❌   |
|                 [OFDConverter](https://github.com/wukonggo/OFDConverter)                  | Apache-2.0 |  ❌  |  ❌  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ✅     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                    [ofdparser](https://github.com/wangyi160/ofdparser)                    |     无     |  ❌  |  ✅  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
| [BootstrapBlazor.OfdReader](https://github.com/BootstrapBlazor/BootstrapBlazor.OfdReader) |    MIT     |  ✅  |  ✅  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                      [Ofd2Pdf](https://github.com/taurusxin/Ofd2Pdf)                      |    MIT     |  ❌  |  ✅  |  ❌  |   ❌   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                      [ofd2pdf](https://github.com/lanbo0829/ofd2pdf)                      |     无     |  ❌  |  ✅  |  ❌  |   ❌   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |

## JavaScript

- [bestofdview](https://github.com/besthqs/bestofdview) - 查看器，支持签章
- [imageConversion](https://github.com/Gary-zy/imageConversion) - OFD/图片/PDF 转换，部分验签支持
- [jit-viewer-sdk](https://github.com/Drexr9558/jit-viewer-sdk) - 商业级查看 SDK
- [jsOFD](https://github.com/Hufe921/jsOFD) - 浏览器内 PDF→OFD（基于 pdf.js），支持生成
- [local-doc-viewer](https://github.com/LocalDoc-Viewer/local-doc-viewer) - Tauri 桌面阅读器（AGPL-3.0）
- [ofd-lzy](https://github.com/Yusuf-dz/ofd-lzy) - 浏览器查看器，支持验签、发票提取与批注（BUSL-1.1）
- [liteofd](https://github.com/SignitDoc/liteofd) - 预览 + 验签 + HTML 输出
- [ofd-online](https://github.com/betgo/ofd-online) - 在线预览，支持 SVG 导出
- [ofd-reader](https://github.com/Maple-pro/ofd-reader) - TypeScript 浏览器阅读器，预览 + 图片导出，HTML 为 Canvas 渲染
- [ofd-to-pdf](https://www.npmjs.com/package/@miconvert/ofd-to-pdf) - OFD→PDF（浏览器/Node），支持发票
- [ofd.js](https://github.com/DLTech21/ofd.js) - 预览 + HTML 输出，部分验签支持
- [ofd.js-js-nuxt](https://github.com/astonmario/ofd.js-js-nuxt) - ofd.js 的服务端渲染版（Nuxt），部分验签支持
- [ofd.js (LaanChae)](https://github.com/LaanChae/ofd.js) - PDF.js 界面，支持 GM/T 0099 加解密、PDF↔OFD 转换及签章验签
- [OFDee](https://github.com/gityongzhong/OFDee) - Tauri 桌面阅读器，自研内核，支持 PNG 与图片型 PDF 导出
- [ofd_editor_frontend](https://github.com/LamplightShadow/ofd_editor_frontend) - 唯一自带编辑器的 JS 库
- [ofdjs](https://github.com/isee15/ofdjs) - 浏览器预览首选，生态最完善
- [ofdjs-viewer](https://github.com/Atw-Lee/ofdjs-viewer) - ofdjs 的查看器实现，支持文本提取
- [ofdviewer](https://github.com/xxss0903/ofdviewer) - 纯前端查看器
- [ofdh5](https://github.com/iwlking/ofdh5) - 移动端 Canvas 预览
- [ofd-to-pdf (campfire)](https://github.com/campfire-code/ofd-to-pdf) - JavaScript OFD→PDF 转换
- [ofdrw-viewer](https://github.com/ofdrw/ofdrw-viewer) - ofdrw 的浏览器查看器，支持打印与全文检索
- [DocPaw-Reader](https://github.com/bushizhuan/DocPaw-Reader) - OFD/H 浏览器阅读器，支持检索、TXT/PNG 导出与打印
- [file-viewer](https://github.com/flyfish-dev/file-viewer) - 多格式浏览器预览，支持 OFD/HTML 输出
- [ofdview](https://github.com/moxudocs/ofdview) - USDOC WASM 浏览器阅读器，支持验签与发票预览
- [OFDView](https://github.com/guinanlin/OFDView) - 预览 + HTML 输出
- [piaopinpin](https://github.com/qq87636108/piaopinpin) - 发票解析与预览
- [webofd](https://github.com/zsc347/webofd) - 在线预览

**能力矩阵**

|                                      库                                       |   许可证   | 预览 | 解析 | 发票 | → 图片 | → PDF | → TXT | → SVG | → Md | → HTML | PDF → OFD | 生成 | 签章 | 加密文档 | 打印 | 检索 | 注释 | 归档 | 修改 | 编辑器 |
|:-----------------------------------------------------------------------------:|:----------:|:----:|:----:|:----:|:------:|:-----:|:-----:|:-----:|:----:|:------:|:---------:|:----:|:----:|:--------:|:----:|:----:|:----:|:----:|:----:|:------:|
|       [ofd-to-pdf](https://www.npmjs.com/package/@miconvert/ofd-to-pdf)       | Apache-2.0 |  ❌  |  ✅  |  ✅  |   ❌   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                   [ofdjs](https://github.com/isee15/ofdjs)                    | Apache-2.0 |  ✅  |  ✅  |  ⚠️  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ✅  |  ❌  |  ❌  |   ❌   |
|         [imageConversion](https://github.com/Gary-zy/imageConversion)         |    MIT     |  ✅  |  ✅  |  ❌  |   ✅   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ⚠️  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                [liteofd](https://github.com/SignitDoc/liteofd)                | Apache-2.0 |  ✅  |  ✅  |  ⚠️  |   ✅   |  ❌   |  ✅   |  ❌   |  ❌  |   ✅   |    ❌     |  ❌  |  ⚠️  |    ❌    |  ❌  |  ✅  |  ✅  |  ❌  |  ❌  |   ❌   |
|             [bestofdview](https://github.com/besthqs/bestofdview)             |     无     |  ✅  |  ✅  |  ❌  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ✅  |    ❌    |  ✅  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                [OFDView](https://github.com/guinanlin/OFDView)                | Apache-2.0 |  ✅  |  ✅  |  ❌  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ✅   |    ❌     |  ❌  |  ❌  |    ❌    |  ✅  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                 [ofd.js](https://github.com/DLTech21/ofd.js)                  | Apache-2.0 |  ✅  |  ✅  |  ⚠️  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ✅   |    ❌     |  ❌  |  ⚠️  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|               [ofd-online](https://github.com/betgo/ofd-online)               |     无     |  ✅  |  ✅  |  ❌  |   ✅   |  ❌   |  ❌   |  ✅   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|              [ofdviewer](https://github.com/xxss0903/ofdviewer)               |    MIT     |  ✅  |  ✅  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                  [webofd](https://github.com/zsc347/webofd)                   |     无     |  ✅  |  ✅  |  ❌  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
| [ofd_editor_frontend](https://github.com/LamplightShadow/ofd_editor_frontend) |     无     |  ✅  |  ✅  |  ❌  |   ✅   |  ✅   |  ❌   |  ❌   |  ❌  |   ⚠️   |    ❌     |  ✅  |  ✅  |    ⚠️    |  ❌  |  ❌  |  ❌  |  ❌  |  ✅  |   ✅   |
|            [ofdjs-viewer](https://github.com/Atw-Lee/ofdjs-viewer)            |    MIT     |  ✅  |  ✅  |  ❌  |   ✅   |  ❌   |  ✅   |  ❌   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ✅  |  ❌  |  ❌  |   ❌   |
|            [piaopinpin](https://github.com/qq87636108/piaopinpin)             |    MIT     |  ✅  |  ✅  |  ✅  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ❌  |    ❌    |  ✅  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|         [jit-viewer-sdk](https://github.com/Drexr9558/jit-viewer-sdk)         | Apache-2.0 |  ✅  |  ✅  |  ⚠️  |   ✅   |  ❌   |  ✅   |  ❌   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ⚠️  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|             [ofd-reader](https://github.com/Maple-pro/ofd-reader)             |     无     |  ✅  |  ✅  |  ⚠️  |   ✅   |  ❌   |  ❌   |  ❌   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ❌  |    ❌    |  ✅  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                   [jsOFD](https://github.com/Hufe921/jsOFD)                   |    MIT     |  ❌  |  ❌  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ✅     |  ✅  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                [ofd-lzy](https://github.com/Yusuf-dz/ofd-lzy)                 |  BUSL-1.1  |  ✅  |  ✅  |  ✅  |   ✅   |  ✅   |  ✅   |  ✅   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ✅  |    ❌    |  ✅  |  ✅  |  ✅  |  ❌  |  ❌  |   ✅   |
|    [local-doc-viewer](https://github.com/LocalDoc-Viewer/local-doc-viewer)    |  AGPL-3.0  |  ✅  |  ✅  |  ⚠️  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|        [ofd.js-js-nuxt](https://github.com/astonmario/ofd.js-js-nuxt)         | Apache-2.0 |  ✅  |  ✅  |  ⚠️  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ✅   |    ❌     |  ❌  |  ⚠️  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                [ofdview](https://github.com/moxudocs/ofdview)                 | Apache-2.0 |  ✅  |  ✅  |  ✅  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ✅  |    ❌    |  ❌  |  ✅  |  ✅  |  ❌  |  ❌  |   ❌   |
|           [file-viewer](https://github.com/flyfish-dev/file-viewer)           | Apache-2.0 |  ✅  |  ✅  |  ⚠️  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ✅   |    ❌     |  ❌  |  ⚠️  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|                   [ofdh5](https://github.com/iwlking/ofdh5)                   |    MIT     |  ✅  |  ✅  |  ❌  |   ❌   |  ❌   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|            [ofd.js (LaanChae)](https://github.com/LaanChae/ofd.js)            |     无     |  ✅  |  ✅  |  ❌  |   ❌   |  ✅   |  ❌   |  ❌   |  ❌  |   ⚠️   |    ✅     |  ❌  |  ✅  |    ✅    |  ✅  |  ✅  |  ✅  |  ❌  |  ✅  |   ⚠️   |
|                [OFDee](https://github.com/gityongzhong/OFDee)                 |    MIT     |  ✅  |  ✅  |  ❌  |   ✅   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|     [ofd-to-pdf (campfire)](https://github.com/campfire-code/ofd-to-pdf)      |    MIT     |  ❌  |  ✅  |  ⚠️  |   ❌   |  ✅   |  ❌   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |
|             [ofdrw-viewer](https://github.com/ofdrw/ofdrw-viewer)             |    MIT     |  ✅  |  ✅  |  ⚠️  |   ✅   |  ❌   |  ✅   |  ❌   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ✅  |    ✅    |  ✅  |  ✅  |  ❌  |  ❌  |  ❌  |   ❌   |
|         [DocPaw-Reader](https://github.com/bushizhuan/DocPaw-Reader)          | Apache-2.0 |  ✅  |  ✅  |  ⚠️  |   ✅   |  ❌   |  ✅   |  ❌   |  ❌  |   ⚠️   |    ❌     |  ❌  |  ⚠️  |    ❌    |  ✅  |  ✅  |  ❌  |  ❌  |  ❌  |   ❌   |

## Pascal

- [tinyofd](https://github.com/miemiekurisu/tinyofd) - 轻量查看器，支持文本提取

**能力矩阵**

|                         库                         |   许可证    | 预览 | 解析 | 发票 | → 图片 | → PDF | → TXT | → SVG | → Md | → HTML | PDF → OFD | 生成 | 签章 | 加密文档 | 打印 | 检索 | 注释 | 归档 | 修改 | 编辑器 |
|:--------------------------------------------------:|:-----------:|:----:|:----:|:----:|:------:|:-----:|:-----:|:-----:|:----:|:------:|:---------:|:----:|:----:|:--------:|:----:|:----:|:----:|:----:|:----:|:------:|
| [tinyofd](https://github.com/miemiekurisu/tinyofd) | PolyForm-NC |  ✅  |  ✅  |  ❌  |   ❌   |  ❌   |  ✅   |  ❌   |  ❌  |   ❌   |    ❌     |  ❌  |  ❌  |    ❌    |  ❌  |  ❌  |  ❌  |  ❌  |  ❌  |   ❌   |

## 选型参考（可能过时）

> 快照日期：**2026-10**。以下为基于 [ofd-benchmark](https://github.com/zc310/ofd-benchmark) 实测与各项目 README 得出的辅助信息，项目更新后可能不再准确，请以仓库最新文档为准。

### 速查

- **至少 12 项能力标为 ✅**：[go-zc310](https://github.com/zc310/ofd)（Go）、[go-ofdgo](https://github.com/xiaoqidun/ofdgo)（Go）、[ofdrw](https://github.com/ofdrw/ofdrw)（Java）、[ofdrw.net](https://github.com/whynpc9/ofdrw.net)（.NET）、[ofd-lzy](https://github.com/Yusuf-dz/ofd-lzy)（JavaScript）
- **仅提供 PDF → OFD 导入**：[OFDConverter](https://github.com/wukonggo/OFDConverter)（.NET）、[pdf2ofd](https://github.com/wanglrebe/pdf2ofd)（Python）、[jsOFD](https://github.com/Hufe921/jsOFD)（JS）
- **附带可视化编辑器**：[go-ofdgo](https://github.com/xiaoqidun/ofdgo)、[OFDEditor](https://github.com/KikyoShaw/OFDEditor)、[ofdEditor](https://github.com/mcoder2014/ofdEditor)、[ofd_editor_frontend](https://github.com/LamplightShadow/ofd_editor_frontend)
- **电子发票相关**：[ofdrw](https://github.com/ofdrw/ofdrw)、[kkFileView](https://github.com/kekingcn/kkFileView)、[easyofd](https://pypi.org/project/easyofd/)、[ofd-to-pdf](https://www.npmjs.com/package/@miconvert/ofd-to-pdf)、[fapiao-print](https://github.com/erma0/fapiao-print)、[piaopinpin](https://github.com/qq87636108/piaopinpin)
- **在线文件预览服务**：[kkFileView](https://github.com/kekingcn/kkFileView)、[JIMU-ConvertPreview](https://github.com/zhangzhen1979/JIMU-ConvertPreview)
- **Blazor / Qt 集成**：[BootstrapBlazor.OfdReader](https://github.com/BootstrapBlazor/BootstrapBlazor.OfdReader)、[ofdEditor](https://github.com/mcoder2014/ofdEditor)

### 已知限制

- **[ofdrw](https://github.com/ofdrw/ofdrw)（Java）**：PDF→OFD 打包需引入 `zip4j`；输出为矢量轮廓/位图，不含可提取文本。
- **[easyofd-rust](https://github.com/easy-4-rust/easyofd-rust)（Rust）**：PDF→OFD 实测可能输出空页、CID 字体乱码、版面固定，体积/速度优势来自内容丢失。
- **[rofd](https://github.com/office-rs/rofd)（Rust）**：→ 图片仅部分支持。
- **[easyofd](https://pypi.org/project/easyofd/)（Python）**：→ PDF 基于图片渲染；实测部分文件会崩溃。
- **[ofd2pdf](https://github.com/jsyzdej/ofd2pdf)（Python）**：基于图片渲染，输出无可提取文本。
- **[ofdjs](https://github.com/isee15/ofdjs)（JS）**：→ HTML 为 Canvas 渲染，不生成 HTML DOM/SVG。
- **[jsOFD](https://github.com/Hufe921/jsOFD)（JS）**：Node <22 需补 `process.getBuiltinModule`；不转换注解/渐变/图案。

## 贡献

欢迎补充与修正。提交 PR 时请：

1. 把条目加入对应语言列表与能力矩阵，按已有维度逐项核对（✅ / ⚠️ / ❌）。
2. 注明**仓库地址**与**许可证**；许可证未明确写「无」。
3. 部分支持请用 ⚠️，并在条目描述中说明限制。
4. 若来自 [ofd-benchmark](https://github.com/zc310/ofd-benchmark) 的基准测试结论（如 PDF→OFD 质量），一并附上说明。
5. 发现能力标注与项目现状不符，欢迎直接提 PR 修正，快照内容也随之更新。

## 说明

- 能力标注基于各项目 README、源码与基准测试结果，可能随版本变化，仅供选型参考。
- 无许可证的项目默认保留所有权利，商业使用需谨慎。
- 清单内容采用 [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/)，代码仓库许可证见 [LICENSE](LICENSE)。
