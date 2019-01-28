---
title: 如何：显式实现两个接口的成员 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: b0725d63f77fbe0b9f3151c0b742777667e93311
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701243"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="f602f-102">如何：显式实现两个接口的成员（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="f602f-102">How to: Explicitly Implement Members of Two Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="f602f-103">显式[接口](../../../csharp/language-reference/keywords/interface.md)实现还允许程序员实现具有相同成员名称的两个接口，并为每个接口成员各提供一个单独的实现。</span><span class="sxs-lookup"><span data-stu-id="f602f-103">Explicit [interface](../../../csharp/language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="f602f-104">本示例同时以公制单位和英制单位显示框的尺寸。</span><span class="sxs-lookup"><span data-stu-id="f602f-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="f602f-105">Box [类](../../../csharp/language-reference/keywords/class.md)实现 IEnglishDimensions 和 IMetricDimensions 两个接口，它们表示不同的度量系统。</span><span class="sxs-lookup"><span data-stu-id="f602f-105">The Box [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="f602f-106">两个接口有相同的成员名称 Length 和 Width。</span><span class="sxs-lookup"><span data-stu-id="f602f-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f602f-107">示例</span><span class="sxs-lookup"><span data-stu-id="f602f-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="f602f-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="f602f-108">Robust Programming</span></span>  
 <span data-ttu-id="f602f-109">如果希望默认度量采用英制单位，请正常实现 Length 和 Width 方法，并从 IMetricDimensions 接口显式实现 Length 和 Width 方法：</span><span class="sxs-lookup"><span data-stu-id="f602f-109">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_2.cs)]  
  
 <span data-ttu-id="f602f-110">这种情况下，可以从类实例访问英制单位，从接口实例访问公制单位：</span><span class="sxs-lookup"><span data-stu-id="f602f-110">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f602f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f602f-111">See also</span></span>

- [<span data-ttu-id="f602f-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f602f-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f602f-113">类和结构</span><span class="sxs-lookup"><span data-stu-id="f602f-113">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="f602f-114">接口</span><span class="sxs-lookup"><span data-stu-id="f602f-114">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
- [<span data-ttu-id="f602f-115">如何：显式实现接口成员</span><span class="sxs-lookup"><span data-stu-id="f602f-115">How to: Explicitly Implement Interface Members</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)
