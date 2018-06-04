---
title: dotnet remove package 命令 - .NET Core CLI
description: dotnet remove package 命令可便于删除对项目的 NuGet 包引用。
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: ed6086bfdfadaa06494c857fc74687f1273af971
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696853"
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

指定项目文件。 如果未指定，此命令会搜索当前目录来获取一个项目文件。

`PACKAGE_NAME`

要删除的包引用。

## <a name="options"></a>选项

`-h|--help`

打印出有关命令的简短帮助。

## <a name="examples"></a>示例

从当前目录中的项目删除 `Newtonsoft.Json` NuGet 包：

`dotnet remove package Newtonsoft.Json`