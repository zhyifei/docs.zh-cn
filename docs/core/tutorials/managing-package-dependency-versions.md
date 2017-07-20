---
title: "如何管理 .NET Core 1.0 的包依赖项版本 | Microsoft Docs"
description: "如何管理 .NET Core 1.0 的包依赖项版本"
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 4424a947-bdf9-4775-8d48-dc350a4e0aee
ms.translationtype: Human Translation
ms.sourcegitcommit: 4437ce5d344cf06d30e31911def6287999fc6ffc
ms.openlocfilehash: 3576fecfd4964bc0a4ca9482888cd61e6ac44350
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017

---

<a id="how-to-manage-package-dependency-versions-for-net-core-10" class="xliff"></a>

# 如何管理 .NET Core 1.0 的包依赖项版本

本文介绍需要了解的 .NET Core 库和应用的包版本信息。

<a id="glossary" class="xliff"></a>

## 词汇表

**修复** - 修复依赖项意味着使用 .NET Core 1.0 NuGet 上发布的相同“系列”的包。

**元包** - 表示一组 NuGet 包的 NuGet 包。

**修整** - 从元包删除不依赖的包的操作。  这与 NuGet 包作者有关。  有关详细信息，请参阅[减少 project.json 的包依赖项](../deploying/reducing-dependencies.md)。 

<a id="fix-your-dependencies-to-net-core-10" class="xliff"></a>

## 将依赖项修复为 .NET Core 1.0

若要可靠地恢复包并编写可靠代码，将依赖项修复为随 .NET Core 1.0 一起提供的包版本，这很重要。  这意味着每个包应具有单个版本，且没有额外的限定符。

**已修复为 1.0 的包示例**

`"System.Collections":"4.0.11"`

`"NETStandard.Library":"1.6.0"`

`"Microsoft.NETCore.App":"1.0.0"`

**未修复为 1.0 的包示例**

`"Microsoft.NETCore.App":"1.0.0-rc4-00454-00"`

`"System.Net.Http":"4.1.0-*"`

`"System.Text.RegularExpressions":"4.0.10-rc3-24021-00"`

<a id="why-does-this-matter" class="xliff"></a>

### 为什么这很重要？

如果将依赖项修复为随 .NET Core 1.0 一起提供的版本，我们保证这些包都可协同运作。  如果使用未通过此方式修复的包，则无法做出这种保证。

<a id="scenarios" class="xliff"></a>

### 方案

虽然所有包及其随 .NET Core 1.0 发布的版本包含在一个大列表中，但如果在某些情况下代码失败，不必逐条查看此列表。

**是否仅依赖** `NETStandard.Library`**？**

如果是，应将 `NETStandard.Library` 包修复为版本 `1.6`。  由于这是策划元包，也会将其闭包修复为 1.0。

**是否仅依赖** `Microsoft.NETCore.App`**？**

如果是，应将 `Microsoft.NETCore.App` 包修复为版本 `1.0.0`。  由于这是策划元包，也会将其闭包修复为 1.0。

**是否[修整](../deploying/reducing-dependencies.md)** `NETStandard.Library` **或** `Microsoft.NETCore.App` **元包依赖项？**

如果是，应确保开始修整的元包也修复为 1.0。  修整后依赖的各个包也修复为 1.0。

**是否依赖** `NETStandard.Library` **或** `Microsoft.NETCore.App` **元包之外的包？**

如果是，需要将其他依赖项修复到 1.0。  请查看本文末尾的正确包版本和生成号。

<a id="a-note-on-using-a-splat-string--when-versioning" class="xliff"></a>

### 版本控制时使用 splat 字符串 (\*) 的注释

你可能已采用了如下所示使用 splat (\*) 字符串的版本控制模式：`"System.Collections":"4.0.11-*"`。

**不应这样做**。  使用 splat 字符串可能会导致从不同的版本恢复包，其中某些版本可能比 .NET Core 1.0 更新。  这可能导致某些包不兼容。

<a id="packages-and-version-numbers-organized-by-metapackage" class="xliff"></a>

## 由元包组织的包和版本号

[所有 .NET 标准库包及其针对 1.0 的版本列表](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt)。

[所有运行时包及其针对 1.0 的版本列表](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt)。

[所有 .NET Core 应用包及其针对 1.0 的版本列表](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt)。

