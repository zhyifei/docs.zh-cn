---
title: "/codepage (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6f4919bc4fc8eda700edbd80fead5b5d9fe0dba1
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="codepage-visual-basic"></a><span data-ttu-id="1f1fe-102">/codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f1fe-102">/codepage (Visual Basic)</span></span>
<span data-ttu-id="1f1fe-103">指定要用于编译中所有源代码文件的代码页。</span><span class="sxs-lookup"><span data-stu-id="1f1fe-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f1fe-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f1fe-104">Syntax</span></span>  
  
```  
/codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="1f1fe-105">参数</span><span class="sxs-lookup"><span data-stu-id="1f1fe-105">Arguments</span></span>  
  
|<span data-ttu-id="1f1fe-106">术语</span><span class="sxs-lookup"><span data-stu-id="1f1fe-106">Term</span></span>|<span data-ttu-id="1f1fe-107">定义</span><span class="sxs-lookup"><span data-stu-id="1f1fe-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="1f1fe-108">必需。</span><span class="sxs-lookup"><span data-stu-id="1f1fe-108">Required.</span></span> <span data-ttu-id="1f1fe-109">编译器将使用指定的代码页`id`解释源代码文件的编码。</span><span class="sxs-lookup"><span data-stu-id="1f1fe-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f1fe-110">备注</span><span class="sxs-lookup"><span data-stu-id="1f1fe-110">Remarks</span></span>  
 <span data-ttu-id="1f1fe-111">若要编译使用特定的编码保存的源代码，可以使用`/codepage`可指定应使用哪个代码页。</span><span class="sxs-lookup"><span data-stu-id="1f1fe-111">To compile source code saved with a specific encoding, you can use `/codepage` to specify which code page should be used.</span></span> <span data-ttu-id="1f1fe-112">`/codepage`选项适用于在编译中的所有源代码文件。</span><span class="sxs-lookup"><span data-stu-id="1f1fe-112">The `/codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="1f1fe-113">有关详细信息，请参阅[.NET Framework 中的字符编码](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9)。</span><span class="sxs-lookup"><span data-stu-id="1f1fe-113">For more information, see [Character Encoding in the .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span></span>  
  
 <span data-ttu-id="1f1fe-114">`/codepage`如果源代码文件均已保存签名中使用的当前 ANSI 代码页、 Unicode 或 utf-8，则不需要选项。</span><span class="sxs-lookup"><span data-stu-id="1f1fe-114">The `/codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="1f1fe-115">保存所有源代码文件的当前 ANSI 代码页与默认情况下，除非用户指定了另一个编码中**编码**对话框。</span><span class="sxs-lookup"><span data-stu-id="1f1fe-115"> saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="1f1fe-116">使用**编码**对话框中，若要打开用不同的代码页保存的源代码文件。</span><span class="sxs-lookup"><span data-stu-id="1f1fe-116"> uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f1fe-117">`/codepage`选项不是可从[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]开发环境中; 只有当从命令行进行编译，它才可用。</span><span class="sxs-lookup"><span data-stu-id="1f1fe-117">The `/codepage` option is not available from within the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f1fe-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f1fe-118">See Also</span></span>  
 [<span data-ttu-id="1f1fe-119">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="1f1fe-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
