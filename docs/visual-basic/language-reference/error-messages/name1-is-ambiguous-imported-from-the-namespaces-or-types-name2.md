---
title: "&lt;name1&gt;是不明确，从命名空间或类型导入&lt;name2&gt;&quot; |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30561
- bc30561
dev_langs:
- VB
helpviewer_keywords:
- BC30561
ms.assetid: 761091f7-1018-4299-b481-3966a4a2c126
caps.latest.revision: 8
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
ms.openlocfilehash: 435689c201452cff2cb9b9532cd70281f3061ec9
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="39ltname1gt39-is-ambiguous-imported-from-the-namespaces-or-types-39ltname2gt39"></a><span data-ttu-id="b85e5-102">&lt;name1&gt;是不明确，从命名空间或类型导入&lt;name2&gt;</span><span class="sxs-lookup"><span data-stu-id="b85e5-102">&#39;&lt;name1&gt;&#39; is ambiguous, imported from the namespaces or types &#39;&lt;name2&gt;&#39;</span></span>
<span data-ttu-id="b85e5-103">你提供的名称不明确，因此与另一个名称冲突。</span><span class="sxs-lookup"><span data-stu-id="b85e5-103">You have provided a name that is ambiguous and therefore conflicts with another name.</span></span> <span data-ttu-id="b85e5-104">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器没有任何冲突解决规则; 您必须自己区分名。</span><span class="sxs-lookup"><span data-stu-id="b85e5-104">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler does not have any conflict resolution rules; you must disambiguate names yourself.</span></span>  
  
 <span data-ttu-id="b85e5-105">**错误 ID:** BC30561</span><span class="sxs-lookup"><span data-stu-id="b85e5-105">**Error ID:** BC30561</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b85e5-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="b85e5-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="b85e5-107">删除命名空间导入，消除名称歧义。</span><span class="sxs-lookup"><span data-stu-id="b85e5-107">Disambiguate the name by removing namespace imports.</span></span>  
  
2.  <span data-ttu-id="b85e5-108">完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="b85e5-108">Fully qualify the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b85e5-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b85e5-109">See Also</span></span>  
 <span data-ttu-id="b85e5-110">[Imports 语句（.NET 命名空间和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="b85e5-110">[Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="b85e5-111"> [在 Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="b85e5-111"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="b85e5-112"> [Namespace 语句](../../../visual-basic/language-reference/statements/namespace-statement.md)</span><span class="sxs-lookup"><span data-stu-id="b85e5-112"> [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md)</span></span>
