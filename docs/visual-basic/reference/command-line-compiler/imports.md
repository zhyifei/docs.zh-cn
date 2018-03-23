---
title: -导入 (Visual Basic)
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d81e9d2bd55e6e38e337805b950a0b85680d129b
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="28a42-102">-导入 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28a42-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="28a42-103">从指定的程序集导入命名空间。</span><span class="sxs-lookup"><span data-stu-id="28a42-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28a42-104">语法</span><span class="sxs-lookup"><span data-stu-id="28a42-104">Syntax</span></span>  
  
```  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="28a42-105">自变量</span><span class="sxs-lookup"><span data-stu-id="28a42-105">Arguments</span></span>  
  
|<span data-ttu-id="28a42-106">术语</span><span class="sxs-lookup"><span data-stu-id="28a42-106">Term</span></span>|<span data-ttu-id="28a42-107">定义</span><span class="sxs-lookup"><span data-stu-id="28a42-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="28a42-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="28a42-108">Required.</span></span> <span data-ttu-id="28a42-109">要导入的命名空间的以逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="28a42-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28a42-110">备注</span><span class="sxs-lookup"><span data-stu-id="28a42-110">Remarks</span></span>  
 <span data-ttu-id="28a42-111">`-imports`选项将导入定义在当前设置的源文件或从任何引用的程序集的任何命名空间。</span><span class="sxs-lookup"><span data-stu-id="28a42-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="28a42-112">使用指定的命名空间中的成员`-imports`可供编译中所有源代码文件。</span><span class="sxs-lookup"><span data-stu-id="28a42-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="28a42-113">使用[Imports 语句 （.NET Namespace 和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)要在单个源代码文件中使用命名空间。</span><span class="sxs-lookup"><span data-stu-id="28a42-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="28a42-114">设置/在 Visual Studio 集成的开发环境中导入</span><span class="sxs-lookup"><span data-stu-id="28a42-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="28a42-115">1.在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="28a42-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="28a42-116">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="28a42-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="28a42-117">2.单击“引用”选项卡。</span><span class="sxs-lookup"><span data-stu-id="28a42-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="28a42-118">3.旁边的框中输入命名空间名称**添加用户导入**按钮。</span><span class="sxs-lookup"><span data-stu-id="28a42-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="28a42-119">4.单击**添加用户导入**按钮。</span><span class="sxs-lookup"><span data-stu-id="28a42-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="28a42-120">示例</span><span class="sxs-lookup"><span data-stu-id="28a42-120">Example</span></span>  
 <span data-ttu-id="28a42-121">下面的代码编译时`/imports:system.globalization`指定。</span><span class="sxs-lookup"><span data-stu-id="28a42-121">The following code compiles when `/imports:system.globalization` is specified.</span></span> <span data-ttu-id="28a42-122">否则，成功编译要求任一`Imports System.Globalization`语句在源代码文件中，开始将包括或属性完全限定为`System.Globalization.CultureInfo.CurrentCulture.Name`。</span><span class="sxs-lookup"><span data-stu-id="28a42-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span> 
  
 [!code-vb[imports example](codesnippet/VisualBasic/imports_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="28a42-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28a42-123">See Also</span></span>  
 [<span data-ttu-id="28a42-124">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="28a42-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="28a42-125">引用和 Imports 语句</span><span class="sxs-lookup"><span data-stu-id="28a42-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="28a42-126">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="28a42-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
