---
title: 使用动态对象 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: ea7d7aae1cd79a0243a9c721b5e3958fba82f84f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832068"
---
# <a name="working-with-dynamic-objects-visual-basic"></a><span data-ttu-id="e666f-102">使用动态对象 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e666f-102">Working with Dynamic Objects (Visual Basic)</span></span>
<span data-ttu-id="e666f-103">动态对象提供另一种方法，而不`Object`类型，将在运行时的后期绑定到一个对象。</span><span class="sxs-lookup"><span data-stu-id="e666f-103">Dynamic objects provide another way, other than the `Object` type, to late bind to an object at run time.</span></span> <span data-ttu-id="e666f-104">通过使用动态中定义的接口在运行时动态对象公开属性和方法等成员<xref:System.Dynamic>命名空间。</span><span class="sxs-lookup"><span data-stu-id="e666f-104">A dynamic object exposes members such as properties and methods at run time by using dynamic interfaces that are defined in the <xref:System.Dynamic> namespace.</span></span> <span data-ttu-id="e666f-105">可以使用中的类<xref:System.Dynamic>命名空间创建的与静态类型或格式不匹配的数据结构处理的对象。</span><span class="sxs-lookup"><span data-stu-id="e666f-105">You can use the classes in the <xref:System.Dynamic> namespace to create objects that work with data structures that do not match a static type or format.</span></span> <span data-ttu-id="e666f-106">此外可以使用 IronPython 和 IronRuby 等动态语言中定义的动态对象。</span><span class="sxs-lookup"><span data-stu-id="e666f-106">You can also use the dynamic objects that are defined in dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="e666f-107">有关演示如何创建动态对象，或使用动态语言中定义的动态对象的示例，请参阅[演练：创建和使用动态对象](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)， <xref:System.Dynamic.DynamicObject>，或<xref:System.Dynamic.ExpandoObject>。</span><span class="sxs-lookup"><span data-stu-id="e666f-107">For examples that show how to create dynamic objects or use a dynamic object defined in a dynamic language, see [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, or <xref:System.Dynamic.ExpandoObject>.</span></span>  
  
 <span data-ttu-id="e666f-108">Visual Basic 将绑定到对象中的动态语言运行时和 IronPython 和 IronRuby 等动态语言使用<xref:System.Dynamic.IDynamicMetaObjectProvider>接口。</span><span class="sxs-lookup"><span data-stu-id="e666f-108">Visual Basic binds to objects from the dynamic language runtime and dynamic languages such as IronPython and IronRuby by using the <xref:System.Dynamic.IDynamicMetaObjectProvider> interface.</span></span> <span data-ttu-id="e666f-109">类的实现示例`IDynamicMetaObjectProvider`接口是<xref:System.Dynamic.DynamicObject>和<xref:System.Dynamic.ExpandoObject>类。</span><span class="sxs-lookup"><span data-stu-id="e666f-109">Examples of classes that implement the `IDynamicMetaObjectProvider` interface are the <xref:System.Dynamic.DynamicObject> and <xref:System.Dynamic.ExpandoObject> classes.</span></span>  
  
 <span data-ttu-id="e666f-110">如果对实现的对象进行后期绑定调用`IDynamicMetaObjectProvider`接口，Visual Basic 将绑定到使用该接口的动态对象。</span><span class="sxs-lookup"><span data-stu-id="e666f-110">If a late-bound call is made to an object that implements the `IDynamicMetaObjectProvider` interface, Visual Basic binds to the dynamic object by using that interface.</span></span> <span data-ttu-id="e666f-111">如果对未实现的对象进行后期绑定调用`IDynamicMetaObjectProvider`接口，或者，如果在调用`IDynamicMetaObjectProvider`接口失败，则通过使用 Visual Basic 运行时的后期绑定功能，Visual Basic 将绑定到对象。</span><span class="sxs-lookup"><span data-stu-id="e666f-111">If a late-bound call is made to an object that does not implement the `IDynamicMetaObjectProvider` interface, or if the call to the `IDynamicMetaObjectProvider` interface fails, Visual Basic binds to the object by using the late-binding capabilities of the Visual Basic runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e666f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="e666f-112">See also</span></span>

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [<span data-ttu-id="e666f-113">演练：创建和使用动态对象</span><span class="sxs-lookup"><span data-stu-id="e666f-113">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [<span data-ttu-id="e666f-114">早期绑定和后期绑定</span><span class="sxs-lookup"><span data-stu-id="e666f-114">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
