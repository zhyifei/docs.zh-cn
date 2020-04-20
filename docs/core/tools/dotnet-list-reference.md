---
title: dotnet list reference 命令
description: dotnet list reference 命令可便于列出项目间引用。
ms.date: 02/14/2020
ms.openlocfilehash: c0ea46298123e69ae527870e50d204d8fcf5cc85
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463650"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

**本文适用于：** ✔️ .NET Core 2.x SDK 及更高版本

## <a name="name"></a>名称

`dotnet list reference` - 列出项目到项目引用。

## <a name="synopsis"></a>摘要

```dotnetcli
dotnet list [<PROJECT>|<SOLUTION>] reference

dotnet list -h|--help
```

## <a name="description"></a>说明

使用 `dotnet list reference` 命令可方便地列出给定项目或解决方案的项目引用。

## <a name="arguments"></a>参数

* **`PROJECT | SOLUTION`**

  指定用于列出引用的项目或解决方案文件。 如果未指定，此命令会搜索当前目录，以获取项目文件。

## <a name="options"></a>选项

* **`-h|--help`**

  打印出有关命令的简短帮助。

## <a name="examples"></a>示例

* 列出指定项目的项目引用：

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* 列出当前目录中的项目的项目引用：

  ```dotnetcli
  dotnet list reference
  ```
