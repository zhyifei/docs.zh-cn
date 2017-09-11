---
title: "-codepage（C# 编译器选项）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /codepage
dev_langs:
- CSharp
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
caps.latest.revision: 15
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
ms.openlocfilehash: b80f6fcf8891d2f0b921af01cc094f624d807aa1
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="codepage-c-compiler-options"></a><span data-ttu-id="6b8e5-102">/codepage（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="6b8e5-102">/codepage (C# Compiler Options)</span></span>
<span data-ttu-id="6b8e5-103">如果所需页不是系统的当前默认代码页，则此选项指定编译期间要使用的代码页。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-103">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b8e5-104">语法</span><span class="sxs-lookup"><span data-stu-id="6b8e5-104">Syntax</span></span>  
  
```console  
/codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="6b8e5-105">参数</span><span class="sxs-lookup"><span data-stu-id="6b8e5-105">Arguments</span></span>  
 `id`  
 <span data-ttu-id="6b8e5-106">要用于编译中所有源代码文件的代码页 ID。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-106">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b8e5-107">备注</span><span class="sxs-lookup"><span data-stu-id="6b8e5-107">Remarks</span></span>  
 <span data-ttu-id="6b8e5-108">如果编译一个或多个并非是为使用计算机上默认代码页而创建的源代码文件，可使用 /codepage 选项指定应使用的代码页。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-108">If you compile one or more source code files that were not created to use the default code page on your computer, you can use the **/codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="6b8e5-109">/codepage 适用于编译中的所有源代码文件。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-109">**/codepage** applies to all source code files in your compilation.</span></span>  
  
 <span data-ttu-id="6b8e5-110">如果源代码文件是使用计算机上采用的相同代码页创建的，或者如果是通过 UNICODE 或 UTF-8 创建的，则无需使用 /codepage。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-110">If the source code files were created with the same codepage that is in effect on your computer or if the source code files were created with UNICODE or UTF-8, you need not use **/codepage**.</span></span>  
  
 <span data-ttu-id="6b8e5-111">有关如何查找系统上支持哪些代码页的信息，请参阅 [GetCPInfo](http://go.microsoft.com/fwlink/?LinkId=148371)。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-111">See [GetCPInfo](http://go.microsoft.com/fwlink/?LinkId=148371) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="6b8e5-112">此编译器选项在 Visual Studio 中不可用，并且无法以编程方式更改。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b8e5-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b8e5-113">See Also</span></span>  
 <span data-ttu-id="6b8e5-114">[（C# 编译器选项）](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="6b8e5-114">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="6b8e5-115">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="6b8e5-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

