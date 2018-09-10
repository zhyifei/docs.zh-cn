---
title: 管理 .NET Core 安装
description: 使用并行安装策略，在计算机上管理多个版本的 .NET Core SDK 和运行时。
author: leecow
ms.author: wiwagn
ms.date: 08/22/2018
ms.openlocfilehash: 06c3f43e7917efb8fd31898044d8f5d920c2cada
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523662"
---
# <a name="manage-net-core-installations"></a>管理 .NET Core 安装

.NET Core 允许多个版本的 SDK 和运行时并行存在，从而为生成和运行 .NET Core 应用程序提供版本依赖关系灵活性。 这些安装和自动版本前滚行为具有相当大的好处，但存在一个明显的缺点。 安装 .NET Core SDK 或 .NET Core 运行时的更新时，以前的版本仍保留在磁盘上。 随着时间的推移，多个安装版本将增加磁盘使用量。 已发布 50 多个 .NET Core SDK 更新。 系统上可能安装了许多可以删除的 SDK 和运行时版本。

## <a name="safe-to-remove"></a>安全删除？

借助 [.NET Core 版本选择](selection.md)行为和 .NET Core 各个更新之间的运行时兼容性，可安全地删除以前的版本。 .NET Core 运行时更新在主版本“区段”（如 1.x 和 2.x）中兼容。 此外，较新版本的 .NET Core SDK 通常能够以兼容的方式生成以运行时的早期版本为目标的应用程序。

通常，只需要应用程序所需的最新 SDK 和运行时的最新补丁版本。 保留旧版 SDK 或运行时版本的实例包括维护基于 project.json 的应用程序。  除非应用程序有需保留早期 SDK 或运行时的特定原因，否则可以安全地删除旧版本。

删除 .NET Core 的方法因平台而异，并且这些方法会根据不同 .NET Core 版本而变化。 要详细了解如何删除不再需要的 .NET Core 版本，请参阅 [.NET Core 文档](../index.md)中的[“如何删除 .NET Core 运行时和 SDK”](remove-runtime-sdk-versions.md)。
