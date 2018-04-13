---
title: 使用动态对象 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: da70c1e4c7398ad46d48c85b62ab884675bd1a73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="working-with-dynamic-objects-visual-basic"></a><span data-ttu-id="fafbe-102">使用动态对象 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fafbe-102">Working with Dynamic Objects (Visual Basic)</span></span>
<span data-ttu-id="fafbe-103">动态对象提供另一种方法，而不`Object`类型，在运行时的后期绑定到对象。</span><span class="sxs-lookup"><span data-stu-id="fafbe-103">Dynamic objects provide another way, other than the `Object` type, to late bind to an object at run time.</span></span> <span data-ttu-id="fafbe-104">使用动态中定义的接口来在运行时的动态对象公开如属性和方法的成员<xref:System.Dynamic>命名空间。</span><span class="sxs-lookup"><span data-stu-id="fafbe-104">A dynamic object exposes members such as properties and methods at run time by using dynamic interfaces that are defined in the <xref:System.Dynamic> namespace.</span></span> <span data-ttu-id="fafbe-105">你可以使用中的类<xref:System.Dynamic>命名空间创建静态类型或格式不匹配的数据结构一起处理的对象。</span><span class="sxs-lookup"><span data-stu-id="fafbe-105">You can use the classes in the <xref:System.Dynamic> namespace to create objects that work with data structures that do not match a static type or format.</span></span> <span data-ttu-id="fafbe-106">你还可以使用 IronPython 和 IronRuby 等的动态语言定义的动态对象。</span><span class="sxs-lookup"><span data-stu-id="fafbe-106">You can also use the dynamic objects that are defined in dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="fafbe-107">有关演示如何创建动态对象，或使用动态语言定义的动态对象的示例，请参阅[演练： 创建和使用动态对象](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)， <xref:System.Dynamic.DynamicObject>，或<xref:System.Dynamic.ExpandoObject>。</span><span class="sxs-lookup"><span data-stu-id="fafbe-107">For examples that show how to create dynamic objects or use a dynamic object defined in a dynamic language, see [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, or <xref:System.Dynamic.ExpandoObject>.</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="fafbe-108">将绑定到对象的动态语言运行时和动态语言，如 IronPython 和 IronRuby 从使用<xref:System.Dynamic.IDynamicMetaObjectProvider>接口。</span><span class="sxs-lookup"><span data-stu-id="fafbe-108"> binds to objects from the dynamic language runtime and dynamic languages such as IronPython and IronRuby by using the <xref:System.Dynamic.IDynamicMetaObjectProvider> interface.</span></span> <span data-ttu-id="fafbe-109">实现的类示例`IDynamicMetaObjectProvider`接口都是<xref:System.Dynamic.DynamicObject>和<xref:System.Dynamic.ExpandoObject>类。</span><span class="sxs-lookup"><span data-stu-id="fafbe-109">Examples of classes that implement the `IDynamicMetaObjectProvider` interface are the <xref:System.Dynamic.DynamicObject> and <xref:System.Dynamic.ExpandoObject> classes.</span></span>  
  
 <span data-ttu-id="fafbe-110">如果到实现的对象进行后期绑定调用`IDynamicMetaObjectProvider`接口，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]将绑定到动态对象，通过该接口。</span><span class="sxs-lookup"><span data-stu-id="fafbe-110">If a late-bound call is made to an object that implements the `IDynamicMetaObjectProvider` interface, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] binds to the dynamic object by using that interface.</span></span> <span data-ttu-id="fafbe-111">如果对不实现的对象进行后期绑定调用`IDynamicMetaObjectProvider`接口，或者，如果调用`IDynamicMetaObjectProvider`接口失败，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]将绑定到对象使用的后期绑定功能[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]运行时。</span><span class="sxs-lookup"><span data-stu-id="fafbe-111">If a late-bound call is made to an object that does not implement the `IDynamicMetaObjectProvider` interface, or if the call to the `IDynamicMetaObjectProvider` interface fails, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] binds to the object by using the late-binding capabilities of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fafbe-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fafbe-112">See Also</span></span>  
 <xref:System.Dynamic.DynamicObject>  
 <xref:System.Dynamic.ExpandoObject>  
 [<span data-ttu-id="fafbe-113">演练：创建和使用动态对象</span><span class="sxs-lookup"><span data-stu-id="fafbe-113">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)  
 [<span data-ttu-id="fafbe-114">早期绑定和后期绑定</span><span class="sxs-lookup"><span data-stu-id="fafbe-114">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
