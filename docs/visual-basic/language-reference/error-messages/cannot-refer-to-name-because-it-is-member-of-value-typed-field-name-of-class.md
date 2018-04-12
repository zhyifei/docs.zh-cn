---
title: 不能引用 &#39;&lt;名称&gt;&#39; 因为它是值类型字段 &#39; 的成员&lt;名称&gt;&#39; 的类 &#39;&lt;类名&gt;&#39; 它具有 &#39;System.MarshalByRefObject &#39;为基类
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a84811b9f0e706cf3ebede09e07c03bd7e4cea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a><span data-ttu-id="e074e-102">不能引用 &#39;&lt;名称&gt;&#39; 因为它是值类型字段 &#39; 的成员&lt;名称&gt;&#39; 的类 &#39;&lt;类名&gt;&#39; 它具有 &#39;System.MarshalByRefObject &#39;为基类</span><span class="sxs-lookup"><span data-stu-id="e074e-102">Cannot refer to &#39;&lt;name&gt;&#39; because it is a member of the value-typed field &#39;&lt;name&gt;&#39; of class &#39;&lt;classname&gt;&#39; which has &#39;System.MarshalByRefObject&#39; as a base class</span></span>
<span data-ttu-id="e074e-103">`System.MarshalByRefObject`类使应用程序支持跨应用程序域边界的远程访问的对象。</span><span class="sxs-lookup"><span data-stu-id="e074e-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="e074e-104">类型必须继承自`MarshalByRejectObject`类时跨应用程序域边界使用的类型。</span><span class="sxs-lookup"><span data-stu-id="e074e-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="e074e-105">因为对象的成员不在其中创建它们的应用程序域之外使用，必须不会复制对象的状态。</span><span class="sxs-lookup"><span data-stu-id="e074e-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="e074e-106">**错误 ID:** BC30310</span><span class="sxs-lookup"><span data-stu-id="e074e-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e074e-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="e074e-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="e074e-108">检查以确保所引用的成员是有效的引用。</span><span class="sxs-lookup"><span data-stu-id="e074e-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2.  <span data-ttu-id="e074e-109">显式限定的成员`Me`关键字。</span><span class="sxs-lookup"><span data-stu-id="e074e-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e074e-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e074e-110">See Also</span></span>  
 <xref:System.MarshalByRefObject>  
 [<span data-ttu-id="e074e-111">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="e074e-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
