---
title: "&#39;&lt;typename&gt;&#39; 不能继承自&lt;类型&gt;&#39;&lt;基类型名称&gt;&#39; 因为它将扩展基访问权限&lt;类型&gt;程序集外部"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords: BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d01981d3136968ae2534539b8eccab4c5c535fbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a><span data-ttu-id="86c62-102">&#39;&lt;typename&gt;&#39; 不能继承自&lt;类型&gt;&#39;&lt;基类型名称&gt;&#39; 因为它将扩展基访问权限&lt;类型&gt;程序集外部</span><span class="sxs-lookup"><span data-stu-id="86c62-102">&#39;&lt;typename&gt;&#39; cannot inherit from &lt;type&gt; &#39;&lt;basetypename&gt;&#39; because it expands the access of the base &lt;type&gt; outside the assembly</span></span>
<span data-ttu-id="86c62-103">类或接口继承自的基类或接口，但是具有限制性较弱的访问级别。</span><span class="sxs-lookup"><span data-stu-id="86c62-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="86c62-104">例如，`Public`接口继承自`Friend`接口，或`Protected`类继承自`Private`类。</span><span class="sxs-lookup"><span data-stu-id="86c62-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="86c62-105">这会公开基类或接口来访问不在预期级别。</span><span class="sxs-lookup"><span data-stu-id="86c62-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="86c62-106">**错误 ID:** BC30910</span><span class="sxs-lookup"><span data-stu-id="86c62-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="86c62-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="86c62-107">To correct this error</span></span>  
  
-   <span data-ttu-id="86c62-108">更改派生的类或接口让至少作为基类或接口的限制性最高的访问级别。</span><span class="sxs-lookup"><span data-stu-id="86c62-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="86c62-109">- 或 -</span><span class="sxs-lookup"><span data-stu-id="86c62-109">-or-</span></span>  
  
-   <span data-ttu-id="86c62-110">如果你需要的限制性较弱的访问级别，删除`Inherits`语句。</span><span class="sxs-lookup"><span data-stu-id="86c62-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="86c62-111">不能从更受限制的基类或接口继承。</span><span class="sxs-lookup"><span data-stu-id="86c62-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86c62-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86c62-112">See Also</span></span>  
 [<span data-ttu-id="86c62-113">Class 语句</span><span class="sxs-lookup"><span data-stu-id="86c62-113">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="86c62-114">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="86c62-114">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="86c62-115">Inherits 语句</span><span class="sxs-lookup"><span data-stu-id="86c62-115">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="86c62-116">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="86c62-116">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
