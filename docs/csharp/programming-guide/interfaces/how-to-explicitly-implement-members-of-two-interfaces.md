---
title: 如何：显式实现两个接口的成员 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: 9e4805f2a9d1a4a18166ea7bcc8fbf8a099e0b9e
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200905"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="e7ff9-102">如何：显式实现两个接口的成员（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="e7ff9-102">How to: Explicitly Implement Members of Two Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="e7ff9-103">显式[接口](../../../csharp/language-reference/keywords/interface.md)实现还允许程序员实现具有相同成员名称的两个接口，并为每个接口成员各提供一个单独的实现。</span><span class="sxs-lookup"><span data-stu-id="e7ff9-103">Explicit [interface](../../../csharp/language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="e7ff9-104">本示例同时以公制单位和英制单位显示框的尺寸。</span><span class="sxs-lookup"><span data-stu-id="e7ff9-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="e7ff9-105">Box [类](../../../csharp/language-reference/keywords/class.md)实现 IEnglishDimensions 和 IMetricDimensions 两个接口，它们表示不同的度量系统。</span><span class="sxs-lookup"><span data-stu-id="e7ff9-105">The Box [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="e7ff9-106">两个接口有相同的成员名称 Length 和 Width。</span><span class="sxs-lookup"><span data-stu-id="e7ff9-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7ff9-107">示例</span><span class="sxs-lookup"><span data-stu-id="e7ff9-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a><span data-ttu-id="e7ff9-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="e7ff9-108">Robust Programming</span></span>  
 <span data-ttu-id="e7ff9-109">如果希望默认度量采用英制单位，请正常实现 Length 和 Width 方法，并从 IMetricDimensions 接口显式实现 Length 和 Width 方法：</span><span class="sxs-lookup"><span data-stu-id="e7ff9-109">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 <span data-ttu-id="e7ff9-110">这种情况下，可以从类实例访问英制单位，从接口实例访问公制单位：</span><span class="sxs-lookup"><span data-stu-id="e7ff9-110">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="e7ff9-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7ff9-111">See also</span></span>

- [<span data-ttu-id="e7ff9-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="e7ff9-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e7ff9-113">类和结构</span><span class="sxs-lookup"><span data-stu-id="e7ff9-113">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="e7ff9-114">接口</span><span class="sxs-lookup"><span data-stu-id="e7ff9-114">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
- [<span data-ttu-id="e7ff9-115">如何：显式实现接口成员</span><span class="sxs-lookup"><span data-stu-id="e7ff9-115">How to: Explicitly Implement Interface Members</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)
