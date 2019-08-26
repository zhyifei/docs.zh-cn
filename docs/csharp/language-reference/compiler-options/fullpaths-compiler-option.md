---
title: -fullpaths（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /fullpaths
helpviewer_keywords:
- /fullpaths compiler option [C#]
- absolute paths [C#]
- fullpaths compiler option [C#]
- full paths [C#]
- -fullpaths compiler option [C#]
ms.assetid: d2a5f857-cbb2-430b-879c-d648aaf0b8c4
ms.openlocfilehash: 3bb4027f1c479bbaedda889d72712acb587b5713
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606866"
---
# <a name="-fullpaths-c-compiler-options"></a><span data-ttu-id="db1c2-102">-fullpaths（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="db1c2-102">-fullpaths (C# Compiler Options)</span></span>
<span data-ttu-id="db1c2-103">-fullpaths 选项导致编译器在列出编译错误和警告时指定文件的完整路径  。</span><span class="sxs-lookup"><span data-stu-id="db1c2-103">The **-fullpaths** option causes the compiler to specify the full path to the file when listing compilation errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db1c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="db1c2-104">Syntax</span></span>  
  
```console  
-fullpaths  
```  
  
## <a name="remarks"></a><span data-ttu-id="db1c2-105">备注</span><span class="sxs-lookup"><span data-stu-id="db1c2-105">Remarks</span></span>  
 <span data-ttu-id="db1c2-106">默认情况下，由编译所产生的错误和警告指定其中发现错误的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="db1c2-106">By default, errors and warnings that result from compilation specify the name of the file in which an error was found.</span></span> <span data-ttu-id="db1c2-107">-fullpaths 选项导致编译器指定文件的完整路径  。</span><span class="sxs-lookup"><span data-stu-id="db1c2-107">The **-fullpaths** option causes the compiler to specify the full path to the file.</span></span>  
  
 <span data-ttu-id="db1c2-108">此编译器选项在 Visual Studio 中不可用，并且无法以编程方式更改。</span><span class="sxs-lookup"><span data-stu-id="db1c2-108">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db1c2-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="db1c2-109">See also</span></span>

- [<span data-ttu-id="db1c2-110">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="db1c2-110">C# Compiler Options</span></span>](./index.md)
