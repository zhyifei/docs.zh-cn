---
title: 如何显式实现接口成员 - C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: dff094aca237ed6146bd9b52813c40549bc99b9b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627780"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="e36ee-102">如何显式实现接口成员（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="e36ee-102">How to explicitly implement interface members (C# Programming Guide)</span></span>
<span data-ttu-id="e36ee-103">本示例声明一个[接口](../../language-reference/keywords/interface.md)`IDimensions` 和一个类 `Box`，显式实现了接口成员 `GetLength` 和 `GetWidth`。</span><span class="sxs-lookup"><span data-stu-id="e36ee-103">This example declares an [interface](../../language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `GetLength` and `GetWidth`.</span></span> <span data-ttu-id="e36ee-104">通过接口实例 `dimensions` 访问这些成员。</span><span class="sxs-lookup"><span data-stu-id="e36ee-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e36ee-105">示例</span><span class="sxs-lookup"><span data-stu-id="e36ee-105">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="e36ee-106">可靠编程</span><span class="sxs-lookup"><span data-stu-id="e36ee-106">Robust Programming</span></span>  
  
- <span data-ttu-id="e36ee-107">请注意，注释掉了 `Main` 方法中以下行，因为它们将产生编译错误。</span><span class="sxs-lookup"><span data-stu-id="e36ee-107">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="e36ee-108">显式实现的接口成员不能从[类](../../language-reference/keywords/class.md)实例访问：</span><span class="sxs-lookup"><span data-stu-id="e36ee-108">An interface member that is explicitly implemented cannot be accessed from a [class](../../language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- <span data-ttu-id="e36ee-109">另请注意 `Main` 方法中的以下行成功输出了框的尺寸，因为这些方法是从接口实例调用的：</span><span class="sxs-lookup"><span data-stu-id="e36ee-109">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a><span data-ttu-id="e36ee-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="e36ee-110">See also</span></span>

- [<span data-ttu-id="e36ee-111">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="e36ee-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e36ee-112">类和结构</span><span class="sxs-lookup"><span data-stu-id="e36ee-112">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="e36ee-113">接口</span><span class="sxs-lookup"><span data-stu-id="e36ee-113">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="e36ee-114">如何显式实现两个接口的成员</span><span class="sxs-lookup"><span data-stu-id="e36ee-114">How to explicitly implement members of two interfaces</span></span>](./how-to-explicitly-implement-members-of-two-interfaces.md)
