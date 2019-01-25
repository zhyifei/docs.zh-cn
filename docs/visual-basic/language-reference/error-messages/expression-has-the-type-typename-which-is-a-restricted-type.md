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
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a>表达式具有类型&#39; &lt;typename&gt; &#39;这是受限的类型，不能用于访问成员继承自&#39;对象&#39;或&#39;ValueType&#39;
一个表达式的计算结果为不能由公共语言运行时 (CLR) 装箱的类型，但访问需要进行装箱的成员。  
  
 *装箱* 是指将一个类型转换为 `Object` ，或有时转换为 <xref:System.ValueType>所需的处理。 公共语言运行时不能装箱某些结构类型，例如<xref:System.ArgIterator>， <xref:System.RuntimeArgumentHandle>，和<xref:System.TypedReference>。  
  
 此表达式将尝试使用受限制的类型来调用的方法继承自<xref:System.Object>或<xref:System.ValueType>，如<xref:System.Object.GetHashCode%2A>或<xref:System.Object.ToString%2A>。 若要访问此方法，Visual Basic 尝试了会导致此错误的隐式装箱转换。  
  
 **错误 ID:** BC31393  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  查找计算结果为引用类型的表达式。  
  
2.  找到您尝试调用从继承的方法的语句的一部分<xref:System.Object>或<xref:System.ValueType>。  
  
3.  重写语句以避免在方法调用。  
  
## <a name="see-also"></a>请参阅
- [隐式转换和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
