---
title: "-fullpaths（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /fullpaths
helpviewer_keywords:
- /fullpaths compiler option [C#]
- absolute paths [C#]
- fullpaths compiler option [C#]
- full paths [C#]
- -fullpaths compiler option [C#]
ms.assetid: d2a5f857-cbb2-430b-879c-d648aaf0b8c4
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8a80a7f5f32aa097802acb932e95e3cd2cd4fdba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="fullpaths-c-compiler-options"></a><span data-ttu-id="8695e-102">/fullpaths（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="8695e-102">/fullpaths (C# Compiler Options)</span></span>
<span data-ttu-id="8695e-103">/fullpaths 选项导致编译器在列出编译错误和警告时指定文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="8695e-103">The **/fullpaths** option causes the compiler to specify the full path to the file when listing compilation errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8695e-104">语法</span><span class="sxs-lookup"><span data-stu-id="8695e-104">Syntax</span></span>  
  
```console  
/fullpaths  
```  
  
## <a name="remarks"></a><span data-ttu-id="8695e-105">备注</span><span class="sxs-lookup"><span data-stu-id="8695e-105">Remarks</span></span>  
 <span data-ttu-id="8695e-106">默认情况下，由编译所产生的错误和警告指定其中发现错误的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="8695e-106">By default, errors and warnings that result from compilation specify the name of the file in which an error was found.</span></span> <span data-ttu-id="8695e-107">/fullpaths 选项导致编译器指定文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="8695e-107">The **/fullpaths** option causes the compiler to specify the full path to the file.</span></span>  
  
 <span data-ttu-id="8695e-108">此编译器选项在 Visual Studio 中不可用，并且无法以编程方式更改。</span><span class="sxs-lookup"><span data-stu-id="8695e-108">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8695e-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8695e-109">See Also</span></span>  
 [<span data-ttu-id="8695e-110">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="8695e-110">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
