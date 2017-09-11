---
title: "表达式具有类型&lt;typename&gt;这是受限的类型，不能用于访问从 Object 或 ValueType 继承的成员 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc31393
- vbc31393
dev_langs:
- VB
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
caps.latest.revision: 6
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
ms.openlocfilehash: b89f7e83bf596c52296a090563d0dd0403ace548
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a><span data-ttu-id="4b947-102">表达式具有类型&lt;typename&gt;这是受限的类型，不能用于访问从 Object 或 ValueType 继承的成员</span><span class="sxs-lookup"><span data-stu-id="4b947-102">Expression has the type &#39;&lt;typename&gt;&#39; which is a restricted type and cannot be used to access members inherited from &#39;Object&#39; or &#39;ValueType&#39;</span></span>
<span data-ttu-id="4b947-103">一个表达式的计算结果为不能由公共语言运行时 (CLR) 装箱的类型，但访问需要装箱的成员。</span><span class="sxs-lookup"><span data-stu-id="4b947-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="4b947-104">*装箱*将 type 转换为所需的处理是指`Object`或有时，到<xref:System.ValueType>。</xref:System.ValueType></span><span class="sxs-lookup"><span data-stu-id="4b947-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="4b947-105">公共语言运行时不能某些结构类型装箱，例如<xref:System.ArgIterator>， <xref:System.RuntimeArgumentHandle>，和<xref:System.TypedReference>。</xref:System.TypedReference> </xref:System.RuntimeArgumentHandle> </xref:System.ArgIterator></span><span class="sxs-lookup"><span data-stu-id="4b947-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="4b947-106">此表达式将尝试使用受限制的类型来调用的方法继承自<xref:System.Object>或<xref:System.ValueType>，如<xref:System.Object.GetHashCode%2A>或<xref:System.Object.ToString%2A>。</xref:System.Object.ToString%2A> </xref:System.Object.GetHashCode%2A> </xref:System.ValueType> </xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="4b947-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="4b947-107">若要访问此方法，[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]已尝试隐式装箱的转换导致此错误。</span><span class="sxs-lookup"><span data-stu-id="4b947-107">To access this method, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="4b947-108">**错误 ID:** BC31393</span><span class="sxs-lookup"><span data-stu-id="4b947-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4b947-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="4b947-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="4b947-110">查找计算结果为引用类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="4b947-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2.  <span data-ttu-id="4b947-111">找到您尝试从<xref:System.Object><xref:System.ValueType>。</xref:System.ValueType>或</xref:System.Object>继承的方法调用的语句的一部分</span><span class="sxs-lookup"><span data-stu-id="4b947-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3.  <span data-ttu-id="4b947-112">重写语句以避免进行方法调用。</span><span class="sxs-lookup"><span data-stu-id="4b947-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b947-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b947-113">See Also</span></span>  
 [<span data-ttu-id="4b947-114">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="4b947-114">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
