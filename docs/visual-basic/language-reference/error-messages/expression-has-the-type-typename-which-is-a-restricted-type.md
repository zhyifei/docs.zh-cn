---
title: 表达式具有类型&#39; &lt;typename&gt; &#39;这是受限的类型，不能用于访问成员继承自&#39;对象&#39;或&#39;ValueType&#39;
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: d44b9a29f0848508d8cd814e857d9b01819ce7ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535952"
---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a><span data-ttu-id="4adbe-102">表达式具有类型&#39; &lt;typename&gt; &#39;这是受限的类型，不能用于访问成员继承自&#39;对象&#39;或&#39;ValueType&#39;</span><span class="sxs-lookup"><span data-stu-id="4adbe-102">Expression has the type &#39;&lt;typename&gt;&#39; which is a restricted type and cannot be used to access members inherited from &#39;Object&#39; or &#39;ValueType&#39;</span></span>
<span data-ttu-id="4adbe-103">一个表达式的计算结果为不能由公共语言运行时 (CLR) 装箱的类型，但访问需要进行装箱的成员。</span><span class="sxs-lookup"><span data-stu-id="4adbe-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="4adbe-104">*装箱* 是指将一个类型转换为 `Object` ，或有时转换为 <xref:System.ValueType>所需的处理。</span><span class="sxs-lookup"><span data-stu-id="4adbe-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="4adbe-105">公共语言运行时不能装箱某些结构类型，例如<xref:System.ArgIterator>， <xref:System.RuntimeArgumentHandle>，和<xref:System.TypedReference>。</span><span class="sxs-lookup"><span data-stu-id="4adbe-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="4adbe-106">此表达式将尝试使用受限制的类型来调用的方法继承自<xref:System.Object>或<xref:System.ValueType>，如<xref:System.Object.GetHashCode%2A>或<xref:System.Object.ToString%2A>。</span><span class="sxs-lookup"><span data-stu-id="4adbe-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="4adbe-107">若要访问此方法，Visual Basic 尝试了会导致此错误的隐式装箱转换。</span><span class="sxs-lookup"><span data-stu-id="4adbe-107">To access this method, Visual Basic has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="4adbe-108">**错误 ID:** BC31393</span><span class="sxs-lookup"><span data-stu-id="4adbe-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4adbe-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="4adbe-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="4adbe-110">查找计算结果为引用类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="4adbe-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2.  <span data-ttu-id="4adbe-111">找到您尝试调用从继承的方法的语句的一部分<xref:System.Object>或<xref:System.ValueType>。</span><span class="sxs-lookup"><span data-stu-id="4adbe-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3.  <span data-ttu-id="4adbe-112">重写语句以避免在方法调用。</span><span class="sxs-lookup"><span data-stu-id="4adbe-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4adbe-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="4adbe-113">See also</span></span>
- [<span data-ttu-id="4adbe-114">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="4adbe-114">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
