---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: fd6240faf702ccb5e543bfd6a7779284f38d8850
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337235"
---
# <a name="-main"></a><span data-ttu-id="2bf99-102">-main</span><span class="sxs-lookup"><span data-stu-id="2bf99-102">-main</span></span>
<span data-ttu-id="2bf99-103">指定包含 `Sub Main` 过程的类或模块。</span><span class="sxs-lookup"><span data-stu-id="2bf99-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bf99-104">语法</span><span class="sxs-lookup"><span data-stu-id="2bf99-104">Syntax</span></span>  
  
```  
-main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="2bf99-105">自变量</span><span class="sxs-lookup"><span data-stu-id="2bf99-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="2bf99-106">必需。</span><span class="sxs-lookup"><span data-stu-id="2bf99-106">Required.</span></span> <span data-ttu-id="2bf99-107">包含模块的类的名称`Sub Main`在程序启动时要调用的过程。</span><span class="sxs-lookup"><span data-stu-id="2bf99-107">The name of the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="2bf99-108">这可能是在窗体 **-主： module**或 **-main:namespace.module**。</span><span class="sxs-lookup"><span data-stu-id="2bf99-108">This may be in the form **-main:module** or **-main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bf99-109">备注</span><span class="sxs-lookup"><span data-stu-id="2bf99-109">Remarks</span></span>  
 <span data-ttu-id="2bf99-110">创建可执行文件或 Windows 可执行程序时，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="2bf99-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="2bf99-111">如果 **-主**省略选项，编译器将搜索有效的共享`Sub Main`所有公共类和模块中。</span><span class="sxs-lookup"><span data-stu-id="2bf99-111">If the **-main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="2bf99-112">请参阅[在 Visual Basic 中的 Main 过程](../../../visual-basic/programming-guide/program-structure/main-procedure.md)有关的各种形式的讨论`Main`过程。</span><span class="sxs-lookup"><span data-stu-id="2bf99-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="2bf99-113">当`location`是一个类，继承自<xref:System.Windows.Forms.Form>，则编译器会提供默认值`Main`如果类没有启动的应用程序的过程`Main`过程。</span><span class="sxs-lookup"><span data-stu-id="2bf99-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="2bf99-114">这样可以在命令行在开发环境中创建的代码编译。</span><span class="sxs-lookup"><span data-stu-id="2bf99-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="2bf99-115">若要设置的主 Visual Studio 集成的开发环境中</span><span class="sxs-lookup"><span data-stu-id="2bf99-115">To set -main in the Visual Studio integrated development environment</span></span>  
  
1. <span data-ttu-id="2bf99-116">在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="2bf99-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2bf99-117">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="2bf99-117">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="2bf99-118">单击“应用程序”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="2bf99-118">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="2bf99-119">请确保**启用应用程序框架**未选中复选框。</span><span class="sxs-lookup"><span data-stu-id="2bf99-119">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4. <span data-ttu-id="2bf99-120">修改中的值**启动对象**框。</span><span class="sxs-lookup"><span data-stu-id="2bf99-120">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bf99-121">示例</span><span class="sxs-lookup"><span data-stu-id="2bf99-121">Example</span></span>  
 <span data-ttu-id="2bf99-122">下面的代码编译`T2.vb`并`T3.vb`，并指定该`Sub Main`过程将在中找到`Test2`类。</span><span class="sxs-lookup"><span data-stu-id="2bf99-122">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="2bf99-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bf99-123">See also</span></span>

- [<span data-ttu-id="2bf99-124">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="2bf99-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2bf99-125">-目标 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2bf99-125">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="2bf99-126">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="2bf99-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="2bf99-127">Visual Basic 中的 Main 过程</span><span class="sxs-lookup"><span data-stu-id="2bf99-127">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
