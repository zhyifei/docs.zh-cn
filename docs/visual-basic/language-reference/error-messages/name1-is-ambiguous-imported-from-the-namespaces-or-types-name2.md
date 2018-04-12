---
title: '&#39;&lt;name1&gt;&#39; 不明确，从命名空间或类型 &#39; 导入&lt;name2&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30561
- bc30561
helpviewer_keywords:
- BC30561
ms.assetid: 761091f7-1018-4299-b481-3966a4a2c126
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6ebc9b75d171a28b4388d48625b772ac6f20dc8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39ltname1gt39-is-ambiguous-imported-from-the-namespaces-or-types-39ltname2gt39"></a><span data-ttu-id="ee888-102">&#39;&lt;name1&gt;&#39; 不明确，从命名空间或类型 &#39; 导入&lt;name2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="ee888-102">&#39;&lt;name1&gt;&#39; is ambiguous, imported from the namespaces or types &#39;&lt;name2&gt;&#39;</span></span>
<span data-ttu-id="ee888-103">你提供的名称不明确，因此与另一个名称冲突。</span><span class="sxs-lookup"><span data-stu-id="ee888-103">You have provided a name that is ambiguous and therefore conflicts with another name.</span></span> <span data-ttu-id="ee888-104">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 编译器没有任何冲突解决规则；你必须自己区分名称。</span><span class="sxs-lookup"><span data-stu-id="ee888-104">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler does not have any conflict resolution rules; you must disambiguate names yourself.</span></span>  
  
 <span data-ttu-id="ee888-105">**错误 ID:** BC30561</span><span class="sxs-lookup"><span data-stu-id="ee888-105">**Error ID:** BC30561</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ee888-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ee888-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="ee888-107">删除命名空间导入，消除名称歧义。</span><span class="sxs-lookup"><span data-stu-id="ee888-107">Disambiguate the name by removing namespace imports.</span></span>  
  
2.  <span data-ttu-id="ee888-108">完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="ee888-108">Fully qualify the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee888-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee888-109">See Also</span></span>  
 [<span data-ttu-id="ee888-110">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="ee888-110">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="ee888-111">在 Visual Basic 中的命名空间</span><span class="sxs-lookup"><span data-stu-id="ee888-111">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="ee888-112">Namespace 语句</span><span class="sxs-lookup"><span data-stu-id="ee888-112">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
