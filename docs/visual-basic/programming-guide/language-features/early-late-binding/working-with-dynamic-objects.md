---
title: 使用动态对象 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 78b17a379ea219cc24842322703caaa9d29eeb2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647344"
---
# <a name="working-with-dynamic-objects-visual-basic"></a><span data-ttu-id="cefc4-102">使用动态对象 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cefc4-102">Working with Dynamic Objects (Visual Basic)</span></span>
<span data-ttu-id="cefc4-103">动态对象提供另一种方法，而不`Object`类型，在运行时的后期绑定到对象。</span><span class="sxs-lookup"><span data-stu-id="cefc4-103">Dynamic objects provide another way, other than the `Object` type, to late bind to an object at run time.</span></span> <span data-ttu-id="cefc4-104">使用动态中定义的接口来在运行时的动态对象公开如属性和方法的成员<xref:System.Dynamic>命名空间。</span><span class="sxs-lookup"><span data-stu-id="cefc4-104">A dynamic object exposes members such as properties and methods at run time by using dynamic interfaces that are defined in the <xref:System.Dynamic> namespace.</span></span> <span data-ttu-id="cefc4-105">你可以使用中的类<xref:System.Dynamic>命名空间创建静态类型或格式不匹配的数据结构一起处理的对象。</span><span class="sxs-lookup"><span data-stu-id="cefc4-105">You can use the classes in the <xref:System.Dynamic> namespace to create objects that work with data structures that do not match a static type or format.</span></span> <span data-ttu-id="cefc4-106">你还可以使用 IronPython 和 IronRuby 等的动态语言定义的动态对象。</span><span class="sxs-lookup"><span data-stu-id="cefc4-106">You can also use the dynamic objects that are defined in dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="cefc4-107">有关演示如何创建动态对象，或使用动态语言定义的动态对象的示例，请参阅[演练： 创建和使用动态对象](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)， <xref:System.Dynamic.DynamicObject>，或<xref:System.Dynamic.ExpandoObject>。</span><span class="sxs-lookup"><span data-stu-id="cefc4-107">For examples that show how to create dynamic objects or use a dynamic object defined in a dynamic language, see [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, or <xref:System.Dynamic.ExpandoObject>.</span></span>  
  
 <span data-ttu-id="cefc4-108">Visual Basic 将绑定到对象的动态语言运行时和动态语言，如 IronPython 和 IronRuby 从使用<xref:System.Dynamic.IDynamicMetaObjectProvider>接口。</span><span class="sxs-lookup"><span data-stu-id="cefc4-108">Visual Basic binds to objects from the dynamic language runtime and dynamic languages such as IronPython and IronRuby by using the <xref:System.Dynamic.IDynamicMetaObjectProvider> interface.</span></span> <span data-ttu-id="cefc4-109">实现的类示例`IDynamicMetaObjectProvider`接口都是<xref:System.Dynamic.DynamicObject>和<xref:System.Dynamic.ExpandoObject>类。</span><span class="sxs-lookup"><span data-stu-id="cefc4-109">Examples of classes that implement the `IDynamicMetaObjectProvider` interface are the <xref:System.Dynamic.DynamicObject> and <xref:System.Dynamic.ExpandoObject> classes.</span></span>  
  
 <span data-ttu-id="cefc4-110">如果到实现的对象进行后期绑定调用`IDynamicMetaObjectProvider`接口，Visual Basic 绑定到通过该接口的动态对象。</span><span class="sxs-lookup"><span data-stu-id="cefc4-110">If a late-bound call is made to an object that implements the `IDynamicMetaObjectProvider` interface, Visual Basic binds to the dynamic object by using that interface.</span></span> <span data-ttu-id="cefc4-111">如果对不实现的对象进行后期绑定调用`IDynamicMetaObjectProvider`接口，或者，如果调用`IDynamicMetaObjectProvider`接口失败，则通过使用 Visual Basic 运行时的后期绑定功能，Visual Basic 将绑定到对象。</span><span class="sxs-lookup"><span data-stu-id="cefc4-111">If a late-bound call is made to an object that does not implement the `IDynamicMetaObjectProvider` interface, or if the call to the `IDynamicMetaObjectProvider` interface fails, Visual Basic binds to the object by using the late-binding capabilities of the Visual Basic runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cefc4-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="cefc4-112">See Also</span></span>  
 <xref:System.Dynamic.DynamicObject>  
 <xref:System.Dynamic.ExpandoObject>  
 [<span data-ttu-id="cefc4-113">演练：创建和使用动态对象</span><span class="sxs-lookup"><span data-stu-id="cefc4-113">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)  
 [<span data-ttu-id="cefc4-114">早期绑定和后期绑定</span><span class="sxs-lookup"><span data-stu-id="cefc4-114">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
