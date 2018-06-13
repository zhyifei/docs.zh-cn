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
ms.openlocfilehash: 29320ae2dc4b13381ecce76fb04101f18d214bba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215305"
---
# <a name="-fullpaths-c-compiler-options"></a><span data-ttu-id="f594d-102">-fullpaths（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="f594d-102">-fullpaths (C# Compiler Options)</span></span>
<span data-ttu-id="f594d-103">-fullpaths 选项导致编译器在列出编译错误和警告时指定文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="f594d-103">The **-fullpaths** option causes the compiler to specify the full path to the file when listing compilation errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f594d-104">语法</span><span class="sxs-lookup"><span data-stu-id="f594d-104">Syntax</span></span>  
  
```console  
-fullpaths  
```  
  
## <a name="remarks"></a><span data-ttu-id="f594d-105">备注</span><span class="sxs-lookup"><span data-stu-id="f594d-105">Remarks</span></span>  
 <span data-ttu-id="f594d-106">默认情况下，由编译所产生的错误和警告指定其中发现错误的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f594d-106">By default, errors and warnings that result from compilation specify the name of the file in which an error was found.</span></span> <span data-ttu-id="f594d-107">-fullpaths 选项导致编译器指定文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="f594d-107">The **-fullpaths** option causes the compiler to specify the full path to the file.</span></span>  
  
 <span data-ttu-id="f594d-108">此编译器选项在 Visual Studio 中不可用，并且无法以编程方式更改。</span><span class="sxs-lookup"><span data-stu-id="f594d-108">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f594d-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="f594d-109">See Also</span></span>  
 [<span data-ttu-id="f594d-110">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="f594d-110">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
