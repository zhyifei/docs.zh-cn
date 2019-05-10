---
title: 类型“<typename>”的“For Each”不明确，因为此类型实现了“System.Collections.Generic.IEnumerable(Of T)”的多个实例化
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: af2340e8e514391503d5f9b706d13ba93336698e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662118"
---
# <a name="for-each-on-type-typename-is-ambiguous-because-the-type-implements-multiple-instantiations-of-systemcollectionsgenericienumerableof-t"></a><span data-ttu-id="124ac-102">For Each 类型\<类型名称 > 不明确，因为该类型实现多个实例化的 System.Collections.Generic.IEnumerable (Of T)</span><span class="sxs-lookup"><span data-stu-id="124ac-102">'For Each' on type '\<typename>' is ambiguous because the type implements multiple instantiations of 'System.Collections.Generic.IEnumerable(Of T)'</span></span>
<span data-ttu-id="124ac-103">一个`For Each`语句指定具有多个迭代器变量<xref:System.Collections.IEnumerable.GetEnumerator%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="124ac-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="124ac-104">迭代器变量必须实现的类型<xref:System.Collections.IEnumerable?displayProperty=nameWithType>或<xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>中的一个接口`Collections`的命名空间[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="124ac-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface in one of the `Collections` namespaces of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="124ac-105">就可以实现多个构造的泛型接口，使用不同的类型参数对每个构造的类。</span><span class="sxs-lookup"><span data-stu-id="124ac-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="124ac-106">如果执行此类用于迭代器变量，该变量将包含多个<xref:System.Collections.IEnumerable.GetEnumerator%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="124ac-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="124ac-107">在这种情况下，Visual Basic 不能选择要调用的方法。</span><span class="sxs-lookup"><span data-stu-id="124ac-107">In such a case, Visual Basic cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="124ac-108">**错误 ID:** BC32096</span><span class="sxs-lookup"><span data-stu-id="124ac-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="124ac-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="124ac-109">To correct this error</span></span>  
  
- <span data-ttu-id="124ac-110">使用[DirectCast 运算符](../../../visual-basic/language-reference/operators/directcast-operator.md)或[TryCast 运算符](../../../visual-basic/language-reference/operators/trycast-operator.md)若要强制转换为接口定义的迭代器变量类型<xref:System.Collections.IEnumerable.GetEnumerator%2A>你想要使用的方法。</span><span class="sxs-lookup"><span data-stu-id="124ac-110">Use [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="124ac-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="124ac-111">See also</span></span>

- [<span data-ttu-id="124ac-112">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="124ac-112">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="124ac-113">接口</span><span class="sxs-lookup"><span data-stu-id="124ac-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
