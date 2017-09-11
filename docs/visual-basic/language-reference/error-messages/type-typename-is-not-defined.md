---
title: "类型 &quot;&lt;typename&gt;&quot; 未定义 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
dev_langs:
- VB
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 18
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
ms.openlocfilehash: 55b76e9d080a2e2e9fe6e9737a713524ea6409f6
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="type-39lttypenamegt39-is-not-defined"></a><span data-ttu-id="ac521-102">类型 '&lt;typename&gt;' 未定义</span><span class="sxs-lookup"><span data-stu-id="ac521-102">Type &#39;&lt;typename&gt;&#39; is not defined</span></span>
<span data-ttu-id="ac521-103">该语句进行了引用未定义的类型。</span><span class="sxs-lookup"><span data-stu-id="ac521-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="ac521-104">您可以如声明语句中定义类型`Enum`， `Structure`， `Class`，或`Interface`。</span><span class="sxs-lookup"><span data-stu-id="ac521-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="ac521-105">**错误 ID:** BC30002</span><span class="sxs-lookup"><span data-stu-id="ac521-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ac521-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ac521-106">To correct this error</span></span>  
  
-   <span data-ttu-id="ac521-107">确保类型定义和它的引用都使用相同的拼写。</span><span class="sxs-lookup"><span data-stu-id="ac521-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
-   <span data-ttu-id="ac521-108">确保该类型定义为引用可访问。</span><span class="sxs-lookup"><span data-stu-id="ac521-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="ac521-109">例如，如果类型在另一个模块，并且已被声明为`Private`、 将该类型定义移到引用的模块或将其声明`Public`。</span><span class="sxs-lookup"><span data-stu-id="ac521-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
-   <span data-ttu-id="ac521-110">请确保该类型的命名空间未在项目中重新定义。</span><span class="sxs-lookup"><span data-stu-id="ac521-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="ac521-111">如果是，使用`Global`关键字用于完全限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="ac521-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="ac521-112">例如，如果一个项目定义命名空间名为`System`、<xref:System.Object?displayProperty=fullName>无法访问类型，除非它是使用完全限定`Global`关键字︰ `Global.System.Object`。</xref:System.Object?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="ac521-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=fullName> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
-   <span data-ttu-id="ac521-113">如果定义的类型，但未注册的对象库或在其中定义的类型库[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]，请单击**添加引用**上**项目**菜单上，然后选择适当的对象库或类型库。</span><span class="sxs-lookup"><span data-stu-id="ac521-113">If the type is defined, but the object library or type library in which it is defined is not registered in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
-   <span data-ttu-id="ac521-114">确保该类型的程序集中的目标.NET Framework 配置文件的一部分。</span><span class="sxs-lookup"><span data-stu-id="ac521-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="ac521-115">有关详细信息，请参阅[疑难解答.NET Framework 目标错误](https://docs.microsoft.com/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors)。</span><span class="sxs-lookup"><span data-stu-id="ac521-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](https://docs.microsoft.com/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac521-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac521-116">See Also</span></span>  
 <span data-ttu-id="ac521-117">[在 Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="ac521-117">[Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="ac521-118"> [Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ac521-118"> [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) </span></span>  
<span data-ttu-id="ac521-119"> [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ac521-119"> [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="ac521-120"> [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ac521-120"> [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) </span></span>  
<span data-ttu-id="ac521-121"> [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ac521-121"> [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) </span></span>  
<span data-ttu-id="ac521-122"> [管理项目中的引用](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)</span><span class="sxs-lookup"><span data-stu-id="ac521-122"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)</span></span>
