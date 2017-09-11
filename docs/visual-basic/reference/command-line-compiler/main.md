---
title: "/main |Microsoft 文档"
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
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: 19
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
ms.openlocfilehash: 61aa78e131ba8903035f630a540f49848f1acd3f
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="main"></a><span data-ttu-id="b3909-102">/main</span><span class="sxs-lookup"><span data-stu-id="b3909-102">/main</span></span>
<span data-ttu-id="b3909-103">指定的类或模块，其中包含`Sub Main`过程。</span><span class="sxs-lookup"><span data-stu-id="b3909-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3909-104">语法</span><span class="sxs-lookup"><span data-stu-id="b3909-104">Syntax</span></span>  
  
```  
/main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="b3909-105">参数</span><span class="sxs-lookup"><span data-stu-id="b3909-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="b3909-106">必需。</span><span class="sxs-lookup"><span data-stu-id="b3909-106">Required.</span></span> <span data-ttu-id="b3909-107">完全限定的类或模块，其中包含位置`Sub Main`在程序启动时要调用的过程。</span><span class="sxs-lookup"><span data-stu-id="b3909-107">A full qualification to the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="b3909-108">这可能是窗体中**/main:module**或**/main:namespace.module**。</span><span class="sxs-lookup"><span data-stu-id="b3909-108">This may be in the form **/main:module** or **/main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3909-109">备注</span><span class="sxs-lookup"><span data-stu-id="b3909-109">Remarks</span></span>  
 <span data-ttu-id="b3909-110">当您创建可执行文件或 Windows 可执行程序时，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="b3909-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="b3909-111">如果**/main**省略选项，编译器将搜索有效的共享`Sub Main`所有公共类和模块中。</span><span class="sxs-lookup"><span data-stu-id="b3909-111">If the **/main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="b3909-112">请参阅[在 Visual Basic 中的 Main 过程](../../../visual-basic/programming-guide/program-structure/main-procedure.md)有关的各种形式的讨论`Main`过程。</span><span class="sxs-lookup"><span data-stu-id="b3909-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="b3909-113">当`location`是一个类，继承自<xref:System.Windows.Forms.Form>，则编译器会提供默认值`Main`如果类没有启动该应用程序的过程`Main`过程。</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="b3909-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="b3909-114">这样就可以在命令行在开发环境中创建的代码编译。</span><span class="sxs-lookup"><span data-stu-id="b3909-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 <span data-ttu-id="b3909-115">[!code-vb[VbVbalrCompiler #&16;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b3909-115">[!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]</span></span>  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="b3909-116">在 Visual Studio 中设置 /main 集成开发环境</span><span class="sxs-lookup"><span data-stu-id="b3909-116">To set /main in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="b3909-117">在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="b3909-117">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b3909-118">在**项目**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="b3909-118">On the **Project** menu, click **Properties**.</span></span>  
  
     <span data-ttu-id="b3909-119">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="b3909-119">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="b3909-120">单击“应用程序” **** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b3909-120">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="b3909-121">请确保**启用应用程序框架**未选中复选框。</span><span class="sxs-lookup"><span data-stu-id="b3909-121">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4.  <span data-ttu-id="b3909-122">在修改此值**启动对象**框。</span><span class="sxs-lookup"><span data-stu-id="b3909-122">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3909-123">示例</span><span class="sxs-lookup"><span data-stu-id="b3909-123">Example</span></span>  
 <span data-ttu-id="b3909-124">下面的代码编译`T2.vb`和`T3.vb`，并指定该`Sub Main`将在中找到过程`Test2`类。</span><span class="sxs-lookup"><span data-stu-id="b3909-124">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3909-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3909-125">See Also</span></span>  
 <span data-ttu-id="b3909-126">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="b3909-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="b3909-127"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="b3909-127"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="b3909-128"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="b3909-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="b3909-129"> [NIB: Hello，World Visual Basic 版本](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c) </span><span class="sxs-lookup"><span data-stu-id="b3909-129"> [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c) </span></span>  
<span data-ttu-id="b3909-130"> [在 Visual Basic 中的 main 过程](../../../visual-basic/programming-guide/program-structure/main-procedure.md)</span><span class="sxs-lookup"><span data-stu-id="b3909-130"> [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)</span></span>
