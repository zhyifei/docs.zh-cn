---
title: 如何：从 Visual Basic 中引用 COM 对象
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f6f7b4887e2cfba65da7a7a890b78c3d6a8508f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="e0482-102">如何：从 Visual Basic 中引用 COM 对象</span><span class="sxs-lookup"><span data-stu-id="e0482-102">How to: Reference COM Objects from Visual Basic</span></span>
<span data-ttu-id="e0482-103">在 Visual Basic 中，添加对具有类型库的 COM 对象的引用需要创建互操作程序集的 COM 库。</span><span class="sxs-lookup"><span data-stu-id="e0482-103">In Visual Basic, adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="e0482-104">对 COM 对象的成员的引用将路由到互操作程序集，然后转发到实际的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="e0482-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="e0482-105">从 COM 对象的响应路由到互操作程序集，并将其转发到你[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="e0482-105">Responses from the COM object are routed to the interop assembly and forwarded to your [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] application.</span></span>  
  
 <span data-ttu-id="e0482-106">您可以无需通过将 COM 对象的类型信息嵌入在.NET 程序集使用互操作程序集引用的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="e0482-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="e0482-107">若要嵌入类型信息，请设置`Embed Interop Types`属性`True`为 COM 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="e0482-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="e0482-108">如果你使用命令行编译器进行编译，请使用`/link`选项来引用 COM 库。</span><span class="sxs-lookup"><span data-stu-id="e0482-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="e0482-109">有关详细信息，请参阅[/link (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/link.md)。</span><span class="sxs-lookup"><span data-stu-id="e0482-109">For more information, see [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span></span>  
  
 <span data-ttu-id="e0482-110">添加对类型库中的集成的开发环境 (IDE) 的引用时，Visual Basic 会自动创建互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="e0482-110">Visual Basic automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="e0482-111">在从命令行处理时，你可以使用 Tlbimp 实用工具来手动创建互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="e0482-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="e0482-112">将引用添加到 COM 对象</span><span class="sxs-lookup"><span data-stu-id="e0482-112">To add references to COM objects</span></span>  
  
1.  <span data-ttu-id="e0482-113">上**项目**菜单上，选择**添加引用**，然后单击**COM**对话框中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="e0482-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2.  <span data-ttu-id="e0482-114">选择你想要从列表中的 COM 对象使用的组件。</span><span class="sxs-lookup"><span data-stu-id="e0482-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3.  <span data-ttu-id="e0482-115">若要简化对互操作程序集的访问，将添加`Imports`到顶部的类或模块，你将在其中使用的 COM 对象的语句。</span><span class="sxs-lookup"><span data-stu-id="e0482-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="e0482-116">例如，下面的代码示例导入命名空间`INKEDLib`中所引用对象`Microsoft InkEdit Control 1.0`库。</span><span class="sxs-lookup"><span data-stu-id="e0482-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="e0482-117">若要创建使用 Tlbimp 为互操作程序集</span><span class="sxs-lookup"><span data-stu-id="e0482-117">To create an interop assembly using Tlbimp</span></span>  
  
1.  <span data-ttu-id="e0482-118">如果尚不搜索路径的一部分，并且你目前不所在的目录，请将 Tlbimp 的位置添加到搜索路径。</span><span class="sxs-lookup"><span data-stu-id="e0482-118">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2.  <span data-ttu-id="e0482-119">调用 Tlbimp 从命令提示符处，提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="e0482-119">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    -   <span data-ttu-id="e0482-120">包含类型库的 DLL 的名称和位置</span><span class="sxs-lookup"><span data-stu-id="e0482-120">Name and location of the DLL that contains the type library</span></span>  
  
    -   <span data-ttu-id="e0482-121">名称和命名空间的位置信息的放置位置</span><span class="sxs-lookup"><span data-stu-id="e0482-121">Name and location of the namespace where the information should be placed</span></span>  
  
    -   <span data-ttu-id="e0482-122">名称和目标互操作程序集的位置</span><span class="sxs-lookup"><span data-stu-id="e0482-122">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="e0482-123">以下代码提供了一个示例：</span><span class="sxs-lookup"><span data-stu-id="e0482-123">The following code provides an example:</span></span>  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="e0482-124">可以使用 Tlbimp 创建互操作程序集的类型库，甚至对于未注册的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="e0482-124">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="e0482-125">但是，由互操作程序集引用的 COM 对象必须正确注册它们将被用于在计算机上。</span><span class="sxs-lookup"><span data-stu-id="e0482-125">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="e0482-126">可以使用 Regsvr32 实用工具随附 Windows 操作系统的系统来注册 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="e0482-126">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0482-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0482-127">See Also</span></span>  
 [<span data-ttu-id="e0482-128">COM 互操作</span><span class="sxs-lookup"><span data-stu-id="e0482-128">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 [<span data-ttu-id="e0482-129">Tlbimp.exe（类型库导入程序）</span><span class="sxs-lookup"><span data-stu-id="e0482-129">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [<span data-ttu-id="e0482-130">Tlbexp.exe（类型库导出程序）</span><span class="sxs-lookup"><span data-stu-id="e0482-130">Tlbexp.exe (Type Library Exporter)</span></span>](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [<span data-ttu-id="e0482-131">演练：使用 COM 对象实现继承</span><span class="sxs-lookup"><span data-stu-id="e0482-131">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [<span data-ttu-id="e0482-132">互操作性疑难解答</span><span class="sxs-lookup"><span data-stu-id="e0482-132">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [<span data-ttu-id="e0482-133">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="e0482-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
