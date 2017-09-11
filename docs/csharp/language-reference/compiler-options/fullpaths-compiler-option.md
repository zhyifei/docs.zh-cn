---
title: "-fullpaths（C# 编译器选项）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /fullpaths
dev_langs:
- CSharp
helpviewer_keywords:
- /fullpaths compiler option [C#]
- absolute paths [C#]
- fullpaths compiler option [C#]
- full paths [C#]
- -fullpaths compiler option [C#]
ms.assetid: d2a5f857-cbb2-430b-879c-d648aaf0b8c4
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: abd78253c44ae1c90241b2ff2bd236513a846384
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="fullpaths-c-compiler-options"></a><span data-ttu-id="d637c-102">/fullpaths（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="d637c-102">/fullpaths (C# Compiler Options)</span></span>
<span data-ttu-id="d637c-103">/fullpaths 选项导致编译器在列出编译错误和警告时指定文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="d637c-103">The **/fullpaths** option causes the compiler to specify the full path to the file when listing compilation errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d637c-104">语法</span><span class="sxs-lookup"><span data-stu-id="d637c-104">Syntax</span></span>  
  
```console  
/fullpaths  
```  
  
## <a name="remarks"></a><span data-ttu-id="d637c-105">备注</span><span class="sxs-lookup"><span data-stu-id="d637c-105">Remarks</span></span>  
 <span data-ttu-id="d637c-106">默认情况下，由编译所产生的错误和警告指定其中发现错误的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d637c-106">By default, errors and warnings that result from compilation specify the name of the file in which an error was found.</span></span> <span data-ttu-id="d637c-107">/fullpaths 选项导致编译器指定文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="d637c-107">The **/fullpaths** option causes the compiler to specify the full path to the file.</span></span>  
  
 <span data-ttu-id="d637c-108">此编译器选项在 Visual Studio 中不可用，并且无法以编程方式更改。</span><span class="sxs-lookup"><span data-stu-id="d637c-108">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d637c-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d637c-109">See Also</span></span>  
 [<span data-ttu-id="d637c-110">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="d637c-110">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)

