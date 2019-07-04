---
title: dotnet list reference 命令
description: dotnet list reference 命令可便于列出项目间引用。
ms.date: 06/26/2019
ms.openlocfilehash: 1f87ff89997cdaa6d0095a4db9f28a2e7cb7e6a9
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67421829"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

**本主题适用于：✓** .NET Core 1.x SDK 及更高版本

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet list reference` - 列出项目到项目引用。

## <a name="synopsis"></a>摘要

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a>说明

使用 `dotnet list reference` 命令可方便地列出给定项目或解决方案的项目引用。

## <a name="arguments"></a>自变量

* **`PROJECT | SOLUTION`**

  指定用于列出引用的项目或解决方案文件。 如果未指定，此命令会搜索当前目录，以获取项目文件。

## <a name="options"></a>选项

* **`-h|--help`**

  打印出有关命令的简短帮助。

## <a name="examples"></a>示例

* 列出指定项目的项目引用：

  ```console
  dotnet list app/app.csproj reference
  ```

* 列出当前目录中的项目的项目引用：

  ```console
  dotnet list reference
  ```
