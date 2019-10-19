---
title: ColorConvertedBitmap 标记扩展
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: 7d14ddc6276b9dd7baee12e267e8af1250bc11ab
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582768"
---
# <a name="colorconvertedbitmap-markup-extension"></a><span data-ttu-id="a0721-102">ColorConvertedBitmap 标记扩展</span><span class="sxs-lookup"><span data-stu-id="a0721-102">ColorConvertedBitmap Markup Extension</span></span>
<span data-ttu-id="a0721-103">提供一种方法，用于指定没有嵌入的配置文件的位图源。</span><span class="sxs-lookup"><span data-stu-id="a0721-103">Provides a way to specify a bitmap source that does not have an embedded profile.</span></span> <span data-ttu-id="a0721-104">颜色上下文/配置文件由 URI 指定，与映像源 URI 相同。</span><span class="sxs-lookup"><span data-stu-id="a0721-104">Color contexts / profiles are specified by URI, as is the image source URI.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="a0721-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="a0721-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="a0721-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="a0721-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`imageSource`|<span data-ttu-id="a0721-107">方式位图的 URI。</span><span class="sxs-lookup"><span data-stu-id="a0721-107">The URI of the nonprofiled bitmap.</span></span>|  
|`sourceIIC`|<span data-ttu-id="a0721-108">源配置文件配置的 URI。</span><span class="sxs-lookup"><span data-stu-id="a0721-108">The URI of the source profile configuration.</span></span>|  
|`destinationIIC`|<span data-ttu-id="a0721-109">目标配置文件配置的 URI</span><span class="sxs-lookup"><span data-stu-id="a0721-109">The URI of the destination profile configuration</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0721-110">备注</span><span class="sxs-lookup"><span data-stu-id="a0721-110">Remarks</span></span>  
 <span data-ttu-id="a0721-111">此标记扩展用于填充一组相关的图像源属性值，如 <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>。</span><span class="sxs-lookup"><span data-stu-id="a0721-111">This markup extension is intended to fill a related set of image-source property values such as <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span></span>  
  
 <span data-ttu-id="a0721-112">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="a0721-112">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="a0721-113">无法在属性元素语法中使用 `ColorConvertedBitmap` （或 `ColorConvertedBitmapExtension`），因为只能将值设置为初始构造函数上的值，这是扩展标识符后面的字符串。</span><span class="sxs-lookup"><span data-stu-id="a0721-113">`ColorConvertedBitmap` (or `ColorConvertedBitmapExtension`) cannot be used in property element syntax, because the values can only be set as values on the initial constructor, which is the string following the extension identifier.</span></span>  
  
 <span data-ttu-id="a0721-114">`ColorConvertedBitmap` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="a0721-114">`ColorConvertedBitmap` is a markup extension.</span></span> <span data-ttu-id="a0721-115">当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。</span><span class="sxs-lookup"><span data-stu-id="a0721-115">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="a0721-116">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。</span><span class="sxs-lookup"><span data-stu-id="a0721-116">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="a0721-117">有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="a0721-117">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0721-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0721-118">See also</span></span>

- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [<span data-ttu-id="a0721-119">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="a0721-119">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="a0721-120">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="a0721-120">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)
