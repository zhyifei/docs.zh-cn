---
title: "XAML 中的 xml:space 处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], whitespace processing
- xml:space attribute [XAML Services]
- whitespace processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
caps.latest.revision: "15"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: a5048cbad1d2ea914d041ac3c87a43223b208c3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="74457-102">XAML 中的 xml:space 处理</span><span class="sxs-lookup"><span data-stu-id="74457-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="74457-103">`xml:space`属性是一个声明对象元素内的有意义的空白处理行为的 XML 定义属性。</span><span class="sxs-lookup"><span data-stu-id="74457-103">The `xml:space` attribute is an XML-defined attribute that declares the significant whitespace processing behavior within an object element.</span></span> <span data-ttu-id="74457-104">此行为是相关的所有内容 （内部文本） 元素中包含其中`xml:space`声明，并且范围给子元素。</span><span class="sxs-lookup"><span data-stu-id="74457-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="74457-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="74457-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="74457-106">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="74457-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="74457-107">备注</span><span class="sxs-lookup"><span data-stu-id="74457-107">Remarks</span></span>  
 <span data-ttu-id="74457-108">定义`xml:space`包括其两个可能值的 XAML 中的特性派生自`xml:space`由 W3C XML 规范定义的"特殊特性"。</span><span class="sxs-lookup"><span data-stu-id="74457-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="74457-109">默认值`xml:space`属性为文本值`"default"`。</span><span class="sxs-lookup"><span data-stu-id="74457-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="74457-110">值`"default"`，或者如果`xml:space`根本未指定，有意义的空白分析的行为是默认的处理，如主题中定义[在 XAML 中的空白处理](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="74457-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant whitespace parsing is the default handling, as defined in the topic [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="74457-111">若要保留在对象元素内容中的空格，请指定`xml:space="preserve"`该的对象元素上。</span><span class="sxs-lookup"><span data-stu-id="74457-111">To preserve whitespace within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="74457-112">在大多数解释下`xml:space`属性效果和属性的值的作用域为子元素。</span><span class="sxs-lookup"><span data-stu-id="74457-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="74457-113">有关 XAML 中的空白处理的完整讨论，请参阅[在 XAML 中的空白处理](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="74457-113">For a complete discussion of whitespace processing in XAML, see [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74457-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74457-114">See Also</span></span>  
 [<span data-ttu-id="74457-115">XAML 中的空白处理</span><span class="sxs-lookup"><span data-stu-id="74457-115">Whitespace Processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [<span data-ttu-id="74457-116">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="74457-116">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
