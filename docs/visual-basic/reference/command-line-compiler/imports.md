---
title: "/imports (Visual Basic 中) |Microsoft 文档"
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
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: 15
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
ms.openlocfilehash: e994e94dcc3cd00f868b6ae90e4c019eb5b9e2eb
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="imports-visual-basic"></a><span data-ttu-id="46e34-102">/imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46e34-102">/imports (Visual Basic)</span></span>
<span data-ttu-id="46e34-103">从指定的程序集导入的命名空间。</span><span class="sxs-lookup"><span data-stu-id="46e34-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46e34-104">语法</span><span class="sxs-lookup"><span data-stu-id="46e34-104">Syntax</span></span>  
  
```  
/imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="46e34-105">参数</span><span class="sxs-lookup"><span data-stu-id="46e34-105">Arguments</span></span>  
  
|<span data-ttu-id="46e34-106">术语</span><span class="sxs-lookup"><span data-stu-id="46e34-106">Term</span></span>|<span data-ttu-id="46e34-107">定义</span><span class="sxs-lookup"><span data-stu-id="46e34-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="46e34-108">必需。</span><span class="sxs-lookup"><span data-stu-id="46e34-108">Required.</span></span> <span data-ttu-id="46e34-109">要导入的命名空间的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="46e34-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46e34-110">备注</span><span class="sxs-lookup"><span data-stu-id="46e34-110">Remarks</span></span>  
 <span data-ttu-id="46e34-111">`/imports`选项将导入在当前设置的源文件或任何引用的程序集中定义的任何命名空间。</span><span class="sxs-lookup"><span data-stu-id="46e34-111">The `/imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="46e34-112">使用指定的命名空间中的成员`/imports`可供在编译中的所有源代码文件。</span><span class="sxs-lookup"><span data-stu-id="46e34-112">The members in a namespace specified with `/imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="46e34-113">使用[Imports 语句 （.NET Namespace 和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)若要在单个源代码文件中使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="46e34-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="46e34-114">若要设置/Visual Studio 集成的开发环境中导入</span><span class="sxs-lookup"><span data-stu-id="46e34-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="46e34-115">1.在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="46e34-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="46e34-116">在**项目**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="46e34-116">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="46e34-117">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="46e34-117">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="46e34-118">2.单击**引用**选项卡。</span><span class="sxs-lookup"><span data-stu-id="46e34-118">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="46e34-119">3.在旁边的框中输入命名空间名称**添加用户导入**按钮。</span><span class="sxs-lookup"><span data-stu-id="46e34-119">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="46e34-120">4.单击**添加用户导入**按钮。</span><span class="sxs-lookup"><span data-stu-id="46e34-120">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="46e34-121">示例</span><span class="sxs-lookup"><span data-stu-id="46e34-121">Example</span></span>  
 <span data-ttu-id="46e34-122">下面的代码编译时`/imports:system`指定。</span><span class="sxs-lookup"><span data-stu-id="46e34-122">The following code compiles when `/imports:system` is specified.</span></span>  
  
 <span data-ttu-id="46e34-123">[!code-vb[VbVbalrCompiler #&21;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="46e34-123">[!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46e34-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46e34-124">See Also</span></span>  
 <span data-ttu-id="46e34-125">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="46e34-125">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="46e34-126"> [引用和 Imports 语句](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span><span class="sxs-lookup"><span data-stu-id="46e34-126"> [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span></span>  
<span data-ttu-id="46e34-127"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="46e34-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
