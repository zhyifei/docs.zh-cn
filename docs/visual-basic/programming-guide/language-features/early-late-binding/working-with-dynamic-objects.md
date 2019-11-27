---
title: 使用动态对象
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 20d007fb48e1db352bab6d8e25d2e60e02554732
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345165"
---
# <a name="working-with-dynamic-objects-visual-basic"></a><span data-ttu-id="12c03-102">使用动态对象 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12c03-102">Working with Dynamic Objects (Visual Basic)</span></span>
<span data-ttu-id="12c03-103">动态对象除了 `Object` 类型之外，还提供了另一种方法，以便在运行时后期绑定到对象。</span><span class="sxs-lookup"><span data-stu-id="12c03-103">Dynamic objects provide another way, other than the `Object` type, to late bind to an object at run time.</span></span> <span data-ttu-id="12c03-104">动态对象通过使用 <xref:System.Dynamic> 命名空间中定义的动态接口，在运行时公开属性和方法等成员。</span><span class="sxs-lookup"><span data-stu-id="12c03-104">A dynamic object exposes members such as properties and methods at run time by using dynamic interfaces that are defined in the <xref:System.Dynamic> namespace.</span></span> <span data-ttu-id="12c03-105">您可以使用 <xref:System.Dynamic> 命名空间中的类来创建对象，这些对象使用与静态类型或格式不匹配的数据结构。</span><span class="sxs-lookup"><span data-stu-id="12c03-105">You can use the classes in the <xref:System.Dynamic> namespace to create objects that work with data structures that do not match a static type or format.</span></span> <span data-ttu-id="12c03-106">还可以使用动态对象（如 IronPython 和 IronRuby）中定义的动态对象。</span><span class="sxs-lookup"><span data-stu-id="12c03-106">You can also use the dynamic objects that are defined in dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="12c03-107">有关演示如何创建动态对象或使用动态语言定义的动态对象的示例，请参阅[演练：创建和使用动态对象](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)、<xref:System.Dynamic.DynamicObject>或 <xref:System.Dynamic.ExpandoObject>。</span><span class="sxs-lookup"><span data-stu-id="12c03-107">For examples that show how to create dynamic objects or use a dynamic object defined in a dynamic language, see [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, or <xref:System.Dynamic.ExpandoObject>.</span></span>  
  
 <span data-ttu-id="12c03-108">Visual Basic 使用 <xref:System.Dynamic.IDynamicMetaObjectProvider> 接口从动态语言运行时和动态语言（例如 IronPython 和 IronRuby）绑定到对象。</span><span class="sxs-lookup"><span data-stu-id="12c03-108">Visual Basic binds to objects from the dynamic language runtime and dynamic languages such as IronPython and IronRuby by using the <xref:System.Dynamic.IDynamicMetaObjectProvider> interface.</span></span> <span data-ttu-id="12c03-109">实现 `IDynamicMetaObjectProvider` 接口的类的示例包括 <xref:System.Dynamic.DynamicObject> 和 <xref:System.Dynamic.ExpandoObject> 类。</span><span class="sxs-lookup"><span data-stu-id="12c03-109">Examples of classes that implement the `IDynamicMetaObjectProvider` interface are the <xref:System.Dynamic.DynamicObject> and <xref:System.Dynamic.ExpandoObject> classes.</span></span>  
  
 <span data-ttu-id="12c03-110">如果对实现 `IDynamicMetaObjectProvider` 接口的对象进行了后期绑定调用，则 Visual Basic 使用该接口绑定到动态对象。</span><span class="sxs-lookup"><span data-stu-id="12c03-110">If a late-bound call is made to an object that implements the `IDynamicMetaObjectProvider` interface, Visual Basic binds to the dynamic object by using that interface.</span></span> <span data-ttu-id="12c03-111">如果对未实现 `IDynamicMetaObjectProvider` 接口的对象进行后期绑定调用，或者对 `IDynamicMetaObjectProvider` 接口的调用失败，Visual Basic 将使用 Visual Basic 运行时的后期绑定功能绑定到该对象。</span><span class="sxs-lookup"><span data-stu-id="12c03-111">If a late-bound call is made to an object that does not implement the `IDynamicMetaObjectProvider` interface, or if the call to the `IDynamicMetaObjectProvider` interface fails, Visual Basic binds to the object by using the late-binding capabilities of the Visual Basic runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12c03-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12c03-112">See also</span></span>

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [<span data-ttu-id="12c03-113">演练：创建和使用动态对象</span><span class="sxs-lookup"><span data-stu-id="12c03-113">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [<span data-ttu-id="12c03-114">早期绑定和后期绑定</span><span class="sxs-lookup"><span data-stu-id="12c03-114">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
