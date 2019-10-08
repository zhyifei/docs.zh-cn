---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: 91f2a27ed9b6fb296dbb9e50fc488fd012311890
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005503"
---
# <a name="-main"></a><span data-ttu-id="2e5f7-102">-main</span><span class="sxs-lookup"><span data-stu-id="2e5f7-102">-main</span></span>
<span data-ttu-id="2e5f7-103">指定包含 `Sub Main` 过程的类或模块。</span><span class="sxs-lookup"><span data-stu-id="2e5f7-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e5f7-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e5f7-104">Syntax</span></span>  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="2e5f7-105">参数</span><span class="sxs-lookup"><span data-stu-id="2e5f7-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="2e5f7-106">必需。</span><span class="sxs-lookup"><span data-stu-id="2e5f7-106">Required.</span></span> <span data-ttu-id="2e5f7-107">类或模块的名称，该类或模块包含在程序启动时要调用的 @no__t。</span><span class="sxs-lookup"><span data-stu-id="2e5f7-107">The name of the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="2e5f7-108">此格式可以是**main： module**或 **-main： namespace。**</span><span class="sxs-lookup"><span data-stu-id="2e5f7-108">This may be in the form **-main:module** or **-main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e5f7-109">备注</span><span class="sxs-lookup"><span data-stu-id="2e5f7-109">Remarks</span></span>  
 <span data-ttu-id="2e5f7-110">创建可执行文件或 Windows 可执行程序时，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="2e5f7-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="2e5f7-111">如果省略 **-main**选项，编译器将在所有公共类和模块中搜索有效的共享 `Sub Main`。</span><span class="sxs-lookup"><span data-stu-id="2e5f7-111">If the **-main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="2e5f7-112">有关 @no__t 过程的各种形式的讨论，请参阅[中的 Main 过程 Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) 。</span><span class="sxs-lookup"><span data-stu-id="2e5f7-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="2e5f7-113">如果 `location` 是继承自 <xref:System.Windows.Forms.Form> 的类，则编译器将提供一个默认的 `Main` 过程，该过程将启动应用程序（如果类没有 @no__t 的过程）。</span><span class="sxs-lookup"><span data-stu-id="2e5f7-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="2e5f7-114">这使您可以在命令行上编译在开发环境中创建的代码。</span><span class="sxs-lookup"><span data-stu-id="2e5f7-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="2e5f7-115">在 Visual Studio 集成开发环境中设置-main</span><span class="sxs-lookup"><span data-stu-id="2e5f7-115">To set -main in the Visual Studio integrated development environment</span></span>  
  
1. <span data-ttu-id="2e5f7-116">在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="2e5f7-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2e5f7-117">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="2e5f7-117">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="2e5f7-118">单击“应用程序” 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2e5f7-118">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="2e5f7-119">请确保未选中 "**启用应用程序框架**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="2e5f7-119">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4. <span data-ttu-id="2e5f7-120">修改 "**启动对象**" 框中的值。</span><span class="sxs-lookup"><span data-stu-id="2e5f7-120">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e5f7-121">示例</span><span class="sxs-lookup"><span data-stu-id="2e5f7-121">Example</span></span>  
 <span data-ttu-id="2e5f7-122">下面的代码编译 `T2.vb` 并 `T3.vb`，指定将在 @no__t 3 类中找到 @no__t 2 过程。</span><span class="sxs-lookup"><span data-stu-id="2e5f7-122">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e5f7-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e5f7-123">See also</span></span>

- [<span data-ttu-id="2e5f7-124">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="2e5f7-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2e5f7-125">-target （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="2e5f7-125">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="2e5f7-126">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="2e5f7-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="2e5f7-127">Visual Basic 中的 Main 过程</span><span class="sxs-lookup"><span data-stu-id="2e5f7-127">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
