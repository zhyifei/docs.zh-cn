---
title: XAML 中的 xml:space 处理
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 886f906b6d1e3a10920dbf52e36bf76324c5a9f2
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432700"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="1de91-102">XAML 中的 xml:space 处理</span><span class="sxs-lookup"><span data-stu-id="1de91-102">xml:space Handling in XAML</span></span>

<span data-ttu-id="1de91-103">该`xml:space`属性是一个 XML 定义的属性，用于声明对象元素中的重要空白处理行为。</span><span class="sxs-lookup"><span data-stu-id="1de91-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="1de91-104">此行为与声明元素`xml:space`中包含的所有内容（内部文本）以及子元素的范围相关。</span><span class="sxs-lookup"><span data-stu-id="1de91-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="1de91-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="1de91-105">XAML Attribute Usage</span></span>

```xaml
<object xml:space="preserve" />
```

 <span data-ttu-id="1de91-106">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="1de91-106">\- or -</span></span>

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a><span data-ttu-id="1de91-107">备注</span><span class="sxs-lookup"><span data-stu-id="1de91-107">Remarks</span></span>

<span data-ttu-id="1de91-108">XAML`xml:space`中属性的定义包括其两个可能的值，由`xml:space`W3C XML 规范定义为"特殊属性"。</span><span class="sxs-lookup"><span data-stu-id="1de91-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>

<span data-ttu-id="1de91-109">属性的`xml:space`默认值是文本值`"default"`。</span><span class="sxs-lookup"><span data-stu-id="1de91-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="1de91-110">对于值`"default"`，或者如果`xml:space`根本不指示，则重要的空白分析行为是默认处理，如[XAML 中的主题白空间处理中](white-space-processing.md)定义的默认处理。</span><span class="sxs-lookup"><span data-stu-id="1de91-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](white-space-processing.md).</span></span>

<span data-ttu-id="1de91-111">要在对象元素内容中保留空白，请在`xml:space="preserve"`该对象元素上指定。</span><span class="sxs-lookup"><span data-stu-id="1de91-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>

<span data-ttu-id="1de91-112">在大多数解释下，`xml:space`属性效果和属性的值范围限定为子元素。</span><span class="sxs-lookup"><span data-stu-id="1de91-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>

<span data-ttu-id="1de91-113">有关 XAML 中空白处理的完整讨论，请参阅[XAML 中的空白处理](white-space-processing.md)。</span><span class="sxs-lookup"><span data-stu-id="1de91-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](white-space-processing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1de91-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="1de91-114">See also</span></span>

- [<span data-ttu-id="1de91-115">XAML 中的空白处理</span><span class="sxs-lookup"><span data-stu-id="1de91-115">White-space processing in XAML</span></span>](white-space-processing.md)
- [<span data-ttu-id="1de91-116">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="1de91-116">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
