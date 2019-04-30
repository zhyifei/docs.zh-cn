---
title: 未定义类型“<typename>”
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: c2675d61307d92da1710368668f43af3559060a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032092"
---
# <a name="type-typename-is-not-defined"></a><span data-ttu-id="69ceb-102">类型\<类型名称 > 未定义</span><span class="sxs-lookup"><span data-stu-id="69ceb-102">Type '\<typename>' is not defined</span></span>
<span data-ttu-id="69ceb-103">该语句进行了对未定义的类型引用。</span><span class="sxs-lookup"><span data-stu-id="69ceb-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="69ceb-104">您可以如声明语句中定义的类型`Enum`， `Structure`， `Class`，或`Interface`。</span><span class="sxs-lookup"><span data-stu-id="69ceb-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="69ceb-105">**错误 ID:** BC30002</span><span class="sxs-lookup"><span data-stu-id="69ceb-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="69ceb-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="69ceb-106">To correct this error</span></span>  
  
- <span data-ttu-id="69ceb-107">请确保该类型定义和它的引用都使用相同的拼写。</span><span class="sxs-lookup"><span data-stu-id="69ceb-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
- <span data-ttu-id="69ceb-108">确保该类型定义为引用可访问。</span><span class="sxs-lookup"><span data-stu-id="69ceb-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="69ceb-109">例如，如果类型是另一个模块中，已声明`Private`、 将类型定义移动到引用的模块，或将其声明`Public`。</span><span class="sxs-lookup"><span data-stu-id="69ceb-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
- <span data-ttu-id="69ceb-110">请确保类型的命名空间不会重新定义你的项目中。</span><span class="sxs-lookup"><span data-stu-id="69ceb-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="69ceb-111">如果是，使用`Global`关键字来完全限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="69ceb-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="69ceb-112">例如，如果一个项目定义名为命名空间`System`，则<xref:System.Object?displayProperty=nameWithType>不能访问类型，除非它是使用完全限定`Global`关键字： `Global.System.Object`。</span><span class="sxs-lookup"><span data-stu-id="69ceb-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
- <span data-ttu-id="69ceb-113">如果定义的类型，但在 Visual Basic 中，单击未注册的对象库或在其中定义的类型库**添加引用**上**项目**菜单，并选择适当的对象库或类型库。</span><span class="sxs-lookup"><span data-stu-id="69ceb-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
- <span data-ttu-id="69ceb-114">请确保该类型所在的目标.NET Framework 配置文件的一部分的程序集。</span><span class="sxs-lookup"><span data-stu-id="69ceb-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="69ceb-115">有关详细信息，请参阅 [.NET Framework 目标错误疑难解答](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors)。</span><span class="sxs-lookup"><span data-stu-id="69ceb-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69ceb-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="69ceb-116">See also</span></span>

- [<span data-ttu-id="69ceb-117">在 Visual Basic 中的命名空间</span><span class="sxs-lookup"><span data-stu-id="69ceb-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="69ceb-118">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="69ceb-118">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="69ceb-119">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="69ceb-119">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="69ceb-120">Class 语句</span><span class="sxs-lookup"><span data-stu-id="69ceb-120">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="69ceb-121">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="69ceb-121">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="69ceb-122">管理项目中的引用</span><span class="sxs-lookup"><span data-stu-id="69ceb-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
