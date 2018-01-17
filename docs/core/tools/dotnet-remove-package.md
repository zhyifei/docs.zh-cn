---
title: "dotnet remove package 命令 - .NET Core CLI"
description: "dotnet remove package 命令可便于删除对项目的 NuGet 包引用。"
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 1bc8d9cdc4db1f103b73116b43e630185a2c35de
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-remove-package"></a>dotnet remove package

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet remove package` - 从项目文件删除包引用。

## <a name="synopsis"></a>摘要

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a>描述

使用 `dotnet remove package` 命令可方便地从项目删除 NuGet 包引用。

## <a name="arguments"></a>自变量

`PROJECT`

指定项目文件。 如果未指定，此命令会搜索当前目录，以获取解决方案文件。

`PACKAGE_NAME`

要删除的包引用。

## <a name="options"></a>选项

`-h|--help`

打印出有关命令的简短帮助。

## <a name="examples"></a>示例

从当前目录中的项目删除 `Newtonsoft.Json` NuGet 包：

`dotnet remove package Newtonsoft.Json`
