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
# <a name="working-with-dynamic-objects-visual-basic"></a>使用动态对象 (Visual Basic)
动态对象提供另一种方法，而不`Object`类型，在运行时的后期绑定到对象。 使用动态中定义的接口来在运行时的动态对象公开如属性和方法的成员<xref:System.Dynamic>命名空间。 你可以使用中的类<xref:System.Dynamic>命名空间创建静态类型或格式不匹配的数据结构一起处理的对象。 你还可以使用 IronPython 和 IronRuby 等的动态语言定义的动态对象。 有关演示如何创建动态对象，或使用动态语言定义的动态对象的示例，请参阅[演练： 创建和使用动态对象](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)， <xref:System.Dynamic.DynamicObject>，或<xref:System.Dynamic.ExpandoObject>。  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]将绑定到对象的动态语言运行时和动态语言，如 IronPython 和 IronRuby 从使用<xref:System.Dynamic.IDynamicMetaObjectProvider>接口。 实现的类示例`IDynamicMetaObjectProvider`接口都是<xref:System.Dynamic.DynamicObject>和<xref:System.Dynamic.ExpandoObject>类。  
  
 如果到实现的对象进行后期绑定调用`IDynamicMetaObjectProvider`接口，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]将绑定到动态对象，通过该接口。 如果对不实现的对象进行后期绑定调用`IDynamicMetaObjectProvider`接口，或者，如果调用`IDynamicMetaObjectProvider`接口失败，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]将绑定到对象使用的后期绑定功能[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]运行时。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Dynamic.DynamicObject>  
 <xref:System.Dynamic.ExpandoObject>  
 [演练：创建和使用动态对象](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)  
 [早期绑定和后期绑定](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
