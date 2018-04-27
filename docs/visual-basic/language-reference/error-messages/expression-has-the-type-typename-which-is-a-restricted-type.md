---
title: 表达式具有类型&#39; &lt;typename&gt; &#39;这是将受限的类型，不能用于访问成员继承自&#39;对象&#39;或&#39;ValueType&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ab4e48c93a6a3c645bf9b5cc6c536d418022ae86
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a><span data-ttu-id="ddb8a-102">表达式具有类型&#39; &lt;typename&gt; &#39;这是将受限的类型，不能用于访问成员继承自&#39;对象&#39;或&#39;ValueType&#39;</span><span class="sxs-lookup"><span data-stu-id="ddb8a-102">Expression has the type &#39;&lt;typename&gt;&#39; which is a restricted type and cannot be used to access members inherited from &#39;Object&#39; or &#39;ValueType&#39;</span></span>
<span data-ttu-id="ddb8a-103">表达式计算结果为不能由公共语言运行库 (CLR) 装箱的类型，但访问需要装箱的成员。</span><span class="sxs-lookup"><span data-stu-id="ddb8a-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="ddb8a-104">*装箱* 是指将一个类型转换为 `Object` ，或有时转换为 <xref:System.ValueType>所需的处理。</span><span class="sxs-lookup"><span data-stu-id="ddb8a-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="ddb8a-105">公共语言运行时不能装箱某些结构类型，例如<xref:System.ArgIterator>， <xref:System.RuntimeArgumentHandle>，和<xref:System.TypedReference>。</span><span class="sxs-lookup"><span data-stu-id="ddb8a-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="ddb8a-106">此表达式尝试使用受限的类型调用的方法继承自<xref:System.Object>或<xref:System.ValueType>，如<xref:System.Object.GetHashCode%2A>或<xref:System.Object.ToString%2A>。</span><span class="sxs-lookup"><span data-stu-id="ddb8a-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="ddb8a-107">若要访问此方法，Visual Basic 已尝试会导致此错误的隐式装箱转换。</span><span class="sxs-lookup"><span data-stu-id="ddb8a-107">To access this method, Visual Basic has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="ddb8a-108">**错误 ID:** BC31393</span><span class="sxs-lookup"><span data-stu-id="ddb8a-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ddb8a-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ddb8a-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="ddb8a-110">查找计算结果为引用类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="ddb8a-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2.  <span data-ttu-id="ddb8a-111">查找语句中尝试调用从继承的方法的部分<xref:System.Object>或<xref:System.ValueType>。</span><span class="sxs-lookup"><span data-stu-id="ddb8a-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3.  <span data-ttu-id="ddb8a-112">重写语句以避免方法调用。</span><span class="sxs-lookup"><span data-stu-id="ddb8a-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddb8a-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddb8a-113">See Also</span></span>  
 [<span data-ttu-id="ddb8a-114">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="ddb8a-114">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
