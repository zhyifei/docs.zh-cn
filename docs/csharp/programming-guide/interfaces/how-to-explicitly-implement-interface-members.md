---
title: 如何：显式实现接口成员（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 5f7ae6bae46cdf6596b206abbdeeb94b5c21a13f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332181"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="f066a-102">如何：显式实现接口成员（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="f066a-102">How to: Explicitly Implement Interface Members (C# Programming Guide)</span></span>
<span data-ttu-id="f066a-103">本示例声明一个[接口](../../../csharp/language-reference/keywords/interface.md) `IDimensions` 和一个类 `Box`，显式实现了接口成员 `getLength` 和 `getWidth`。</span><span class="sxs-lookup"><span data-stu-id="f066a-103">This example declares an [interface](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `getLength` and `getWidth`.</span></span> <span data-ttu-id="f066a-104">通过接口实例 `dimensions` 访问这些成员。</span><span class="sxs-lookup"><span data-stu-id="f066a-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f066a-105">示例</span><span class="sxs-lookup"><span data-stu-id="f066a-105">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="f066a-106">可靠编程</span><span class="sxs-lookup"><span data-stu-id="f066a-106">Robust Programming</span></span>  
  
-   <span data-ttu-id="f066a-107">请注意，注释掉了 `Main` 方法中以下行，因为它们将产生编译错误。</span><span class="sxs-lookup"><span data-stu-id="f066a-107">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="f066a-108">显式实现的接口成员不能从[类](../../../csharp/language-reference/keywords/class.md)实例访问：</span><span class="sxs-lookup"><span data-stu-id="f066a-108">An interface member that is explicitly implemented cannot be accessed from a [class](../../../csharp/language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]  
  
-   <span data-ttu-id="f066a-109">另请注意 `Main` 方法中的以下行成功输出了框的尺寸，因为这些方法是从接口实例调用的：</span><span class="sxs-lookup"><span data-stu-id="f066a-109">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f066a-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="f066a-110">See Also</span></span>  
 [<span data-ttu-id="f066a-111">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f066a-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f066a-112">类和结构</span><span class="sxs-lookup"><span data-stu-id="f066a-112">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="f066a-113">接口</span><span class="sxs-lookup"><span data-stu-id="f066a-113">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
 [<span data-ttu-id="f066a-114">如何：显式实现两个接口的成员</span><span class="sxs-lookup"><span data-stu-id="f066a-114">How to: Explicitly Implement Members of Two Interfaces</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)
