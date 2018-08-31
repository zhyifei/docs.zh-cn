---
title: .NET Core 版本历史记录
description: 请参阅 .NET Core 运行时、.NET Core SDK、C# 编译器和 VB.NET 编译器版本的时间线。
ms.date: 07/26/2018
ms.openlocfilehash: 90fd4ba57620a3a005f2148c0335a76a6fa54a30
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42936633"
---
# <a name="net-core-version-history"></a>NET Core 版本历史记录

处理 .NET Core 的版本号有一定难度，因为 .NET Core SDK 和.NET Core Runtime 的发布节奏不同。 节奏不同意味着团队只能完成以下三项中的其中两项：

1. 独立发布，具体来说是允许工具、C# 和 VB 先于 .NET Core Runtime。
2. 保持 .NET Core SDK 和 .NET Core Runtime 之间的版本号一致。
3. 对 .NET Core SDK 和 .NET Core Runtime 使用语义版本控制。

2.0.0 强制执行版本一致性并顺利发布。 2017 年 12 月，.NET Core SDK 进行了一次功能发布，而 .NET Core Runtime 没有相应的发布。 团队选择了目标 1 和 3，没有保持 .NET Core Runtime 和 SDK 之间的一致性。 在 .NET Core Runtime 2.1 之前发布了几个 .NET Core SDK 2.1.x 版本。 由于 SDK 不是向前兼容，因此这些 2.1.x SDK 版本无法面向 .NET Core Runtime 2.1。 该团队为了应对大量混乱，切换到目标 1 和 2，放弃了 [.NET Core 版本控制](index.md#versioning-details)中所述的语义版本控制。

由于决定放弃语义版本控制的时间选择，2.1.10x 和 2.1.20x 版本号范围内存在过渡版本，这些版本也无法面向 .NET Core Runtime 2.1。

版本号的前两位数字与 .NET Core Runtime 的 2.1.0 版本和 .NET Core SDK 的 2.1.300 版本重新保持一致。

可在 [.NET Core 下载页](https://www.microsoft.com/net/download/dotnet-core/current)上找到有关各个组件版本（包括框架和语言编译器版本）的详细信息。 有关以前版本的详细信息，请从 [.NET Core 下载归档页](https://www.microsoft.com/net/download/archives)中选择所请求的版本。 可在描述官方 [.NET 支持策略](https://www.microsoft.com/net/Support/Policy)的文章中找到详细的支持信息。