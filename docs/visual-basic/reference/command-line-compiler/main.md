---
title: /main
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2697b837a536b1b879196bd10843a2b76314747a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="main"></a><span data-ttu-id="1463b-102">/main</span><span class="sxs-lookup"><span data-stu-id="1463b-102">/main</span></span>
<span data-ttu-id="1463b-103">指定包含 `Sub Main` 过程的类或模块。</span><span class="sxs-lookup"><span data-stu-id="1463b-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1463b-104">语法</span><span class="sxs-lookup"><span data-stu-id="1463b-104">Syntax</span></span>  
  
```  
/main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="1463b-105">参数</span><span class="sxs-lookup"><span data-stu-id="1463b-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="1463b-106">必需。</span><span class="sxs-lookup"><span data-stu-id="1463b-106">Required.</span></span> <span data-ttu-id="1463b-107">完全限定位置的类或模块包含`Sub Main`在程序启动时要调用的过程。</span><span class="sxs-lookup"><span data-stu-id="1463b-107">A full qualification to the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="1463b-108">这可能是窗体中**/main:module**或**/main:namespace.module**。</span><span class="sxs-lookup"><span data-stu-id="1463b-108">This may be in the form **/main:module** or **/main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1463b-109">备注</span><span class="sxs-lookup"><span data-stu-id="1463b-109">Remarks</span></span>  
 <span data-ttu-id="1463b-110">在创建可执行文件或 Windows 可执行程序时，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="1463b-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="1463b-111">如果**/主要**省略选项，编译器将搜索有效的共享`Sub Main`所有公共类和模块中。</span><span class="sxs-lookup"><span data-stu-id="1463b-111">If the **/main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="1463b-112">请参阅[Visual Basic 中的 Main 过程](../../../visual-basic/programming-guide/program-structure/main-procedure.md)有关的各种形式的讨论`Main`过程。</span><span class="sxs-lookup"><span data-stu-id="1463b-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="1463b-113">当`location`是继承自的类<xref:System.Windows.Forms.Form>，则编译器会提供默认`Main`如果类没有启动的应用程序的过程`Main`过程。</span><span class="sxs-lookup"><span data-stu-id="1463b-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="1463b-114">这样，你将在命令行在开发环境中创建的代码编译。</span><span class="sxs-lookup"><span data-stu-id="1463b-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="1463b-115">在 Visual Studio 中设置 /main 集成开发环境</span><span class="sxs-lookup"><span data-stu-id="1463b-115">To set /main in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="1463b-116">在 “解决方案资源管理器”中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="1463b-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="1463b-117">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="1463b-117">On the **Project** menu, click **Properties**.</span></span>  
  
     <span data-ttu-id="1463b-118">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="1463b-118">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="1463b-119">单击“应用程序”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="1463b-119">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="1463b-120">请确保**启用应用程序框架**未选中复选框。</span><span class="sxs-lookup"><span data-stu-id="1463b-120">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4.  <span data-ttu-id="1463b-121">修改中的值**启动对象**框。</span><span class="sxs-lookup"><span data-stu-id="1463b-121">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1463b-122">示例</span><span class="sxs-lookup"><span data-stu-id="1463b-122">Example</span></span>  
 <span data-ttu-id="1463b-123">下面的代码编译`T2.vb`和`T3.vb`，并指定，`Sub Main`将在中找到过程`Test2`类。</span><span class="sxs-lookup"><span data-stu-id="1463b-123">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="1463b-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1463b-124">See Also</span></span>  
 [<span data-ttu-id="1463b-125">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="1463b-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="1463b-126">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1463b-126">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="1463b-127">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="1463b-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="1463b-128">Hello，World NIB: Visual Basic 版本</span><span class="sxs-lookup"><span data-stu-id="1463b-128">NIB: Visual Basic Version of Hello, World</span></span>](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)  
 [<span data-ttu-id="1463b-129">Visual Basic 中的 main 过程</span><span class="sxs-lookup"><span data-stu-id="1463b-129">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
