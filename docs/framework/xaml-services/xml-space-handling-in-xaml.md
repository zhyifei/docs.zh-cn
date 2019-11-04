---
title: XAML 中的 xml:space 处理
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 8f860f5ee42b5c1df43c4ec2b1003408bc1c0d8e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458803"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="dcbe2-102">XAML 中的 xml:space 处理</span><span class="sxs-lookup"><span data-stu-id="dcbe2-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="dcbe2-103">`xml:space` 特性是一个 XML 定义的特性，用于声明对象元素内的有效空白处理行为。</span><span class="sxs-lookup"><span data-stu-id="dcbe2-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="dcbe2-104">此行为与在其中声明了 `xml:space` 的元素中包含的所有内容（内部文本）有关，并且还适用于子元素。</span><span class="sxs-lookup"><span data-stu-id="dcbe2-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="dcbe2-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="dcbe2-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="dcbe2-106">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="dcbe2-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="dcbe2-107">备注</span><span class="sxs-lookup"><span data-stu-id="dcbe2-107">Remarks</span></span>  
 <span data-ttu-id="dcbe2-108">XAML 中的 `xml:space` 属性（包括其两个可能的值）的定义是从定义为 "特殊特性" 的 `xml:space` 派生的，由 W3C for XML 规范定义。</span><span class="sxs-lookup"><span data-stu-id="dcbe2-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="dcbe2-109">`xml:space` 属性的默认值为 `"default"`的文本值。</span><span class="sxs-lookup"><span data-stu-id="dcbe2-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="dcbe2-110">对于 `"default"`的值，或者，如果根本没有指示 `xml:space`，则有效的空白分析的行为是默认处理，如在[XAML 中的空白处理](whitespace-processing-in-xaml.md)中定义的那样。</span><span class="sxs-lookup"><span data-stu-id="dcbe2-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="dcbe2-111">若要保留对象元素内容中的空格，请在该对象元素上指定 `xml:space="preserve"`。</span><span class="sxs-lookup"><span data-stu-id="dcbe2-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="dcbe2-112">在大多数解释下，属性的 `xml:space` 属性效果和属性值的作用域为子元素。</span><span class="sxs-lookup"><span data-stu-id="dcbe2-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="dcbe2-113">有关 XAML 中的空白处理的完整讨论，请参阅[xaml 中的空白处理](whitespace-processing-in-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="dcbe2-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcbe2-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="dcbe2-114">See also</span></span>

- [<span data-ttu-id="dcbe2-115">XAML 中的空白处理</span><span class="sxs-lookup"><span data-stu-id="dcbe2-115">White-space processing in XAML</span></span>](whitespace-processing-in-xaml.md)
- [<span data-ttu-id="dcbe2-116">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="dcbe2-116">XAML Overview (WPF)</span></span>](../../desktop-wpf/fundamentals/xaml.md)
