---
title: 如何：向墨迹数据添加自定义数据
ms.date: 03/30/2017
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
ms.openlocfilehash: 40d883f3d3e1d504c8757c31325aa72a03da37e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544506"
---
# <a name="how-to-add-custom-data-to-ink-data"></a><span data-ttu-id="ab2a5-102">如何：向墨迹数据添加自定义数据</span><span class="sxs-lookup"><span data-stu-id="ab2a5-102">How to: Add Custom Data to Ink Data</span></span>
<span data-ttu-id="ab2a5-103">可以将自定义数据添加到墨迹保存为墨迹序列化格式 (ISF) 时将保存的墨迹。</span><span class="sxs-lookup"><span data-stu-id="ab2a5-103">You can add custom data to ink that will be saved when the ink is saved as ink serialized format (ISF).</span></span>  <span data-ttu-id="ab2a5-104">你可以自定义将数据保存到<xref:System.Windows.Ink.DrawingAttributes>、 <xref:System.Windows.Ink.StrokeCollection>，或<xref:System.Windows.Ink.Stroke>。</span><span class="sxs-lookup"><span data-stu-id="ab2a5-104">You can save the custom data to the <xref:System.Windows.Ink.DrawingAttributes>, the <xref:System.Windows.Ink.StrokeCollection>, or the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="ab2a5-105">能够将自定义数据保存在三个对象上使你能够决定最佳的位置来保存的数据。</span><span class="sxs-lookup"><span data-stu-id="ab2a5-105">Being able to save custom data on three objects gives you the ability to decide the best place to save the data.</span></span>  <span data-ttu-id="ab2a5-106">所有三个类使用类似的方法来存储和访问自定义数据。</span><span class="sxs-lookup"><span data-stu-id="ab2a5-106">All three classes use similar methods to store and access custom data.</span></span>  
  
 <span data-ttu-id="ab2a5-107">只能使用以下类型可以另存为自定义数据：</span><span class="sxs-lookup"><span data-stu-id="ab2a5-107">Only the following types can be saved as custom data:</span></span>  
  
-   <xref:System.Boolean>  
  
-   <span data-ttu-id="ab2a5-108"><xref:System.Boolean>[]</span><span class="sxs-lookup"><span data-stu-id="ab2a5-108"><xref:System.Boolean>[]</span></span>  
  
-   <xref:System.Byte>  
  
-   <span data-ttu-id="ab2a5-109"><xref:System.Byte>[]</span><span class="sxs-lookup"><span data-stu-id="ab2a5-109"><xref:System.Byte>[]</span></span>  
  
-   <xref:System.Char>  
  
-   <span data-ttu-id="ab2a5-110"><xref:System.Char>[]</span><span class="sxs-lookup"><span data-stu-id="ab2a5-110"><xref:System.Char>[]</span></span>  
  
-   <xref:System.DateTime>  
  
-   <span data-ttu-id="ab2a5-111"><xref:System.DateTime>[]</span><span class="sxs-lookup"><span data-stu-id="ab2a5-111"><xref:System.DateTime>[]</span></span>  
  
-   <xref:System.Decimal>  
  
-   <span data-ttu-id="ab2a5-112"><xref:System.Decimal>[]</span><span class="sxs-lookup"><span data-stu-id="ab2a5-112"><xref:System.Decimal>[]</span></span>  
  
-   <xref:System.Double>  
  
-   <span data-ttu-id="ab2a5-113"><xref:System.Double>[]</span><span class="sxs-lookup"><span data-stu-id="ab2a5-113"><xref:System.Double>[]</span></span>  
  
-   <xref:System.Int16>  
  
-   <span data-ttu-id="ab2a5-114"><xref:System.Int16>[]</span><span class="sxs-lookup"><span data-stu-id="ab2a5-114"><xref:System.Int16>[]</span></span>  
  
-   <xref:System.Int32>  
  
-   <span data-ttu-id="ab2a5-115"><xref:System.Int32>[]</span><span class="sxs-lookup"><span data-stu-id="ab2a5-115"><xref:System.Int32>[]</span></span>  
  
-   <xref:System.Int64>  
  
-   <span data-ttu-id="ab2a5-116"><xref:System.Int64>[]</span><span class="sxs-lookup"><span data-stu-id="ab2a5-116"><xref:System.Int64>[]</span></span>  
  
-   <xref:System.Single>  
  
-   <span data-ttu-id="ab2a5-117"><xref:System.Single>[]</span><span class="sxs-lookup"><span data-stu-id="ab2a5-117"><xref:System.Single>[]</span></span>  
  
-   <xref:System.String>  
  
-   <xref:System.UInt16>  
  
-   <span data-ttu-id="ab2a5-118"><xref:System.UInt16>[]</span><span class="sxs-lookup"><span data-stu-id="ab2a5-118"><xref:System.UInt16>[]</span></span>  
  
-   <xref:System.UInt32>  
  
-   <span data-ttu-id="ab2a5-119"><xref:System.UInt32>[]</span><span class="sxs-lookup"><span data-stu-id="ab2a5-119"><xref:System.UInt32>[]</span></span>  
  
-   <xref:System.UInt64>  
  
-   <span data-ttu-id="ab2a5-120"><xref:System.UInt64>[]</span><span class="sxs-lookup"><span data-stu-id="ab2a5-120"><xref:System.UInt64>[]</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab2a5-121">示例</span><span class="sxs-lookup"><span data-stu-id="ab2a5-121">Example</span></span>  
 <span data-ttu-id="ab2a5-122">下面的示例演示如何添加和检索自定义数据从<xref:System.Windows.Ink.StrokeCollection>。</span><span class="sxs-lookup"><span data-stu-id="ab2a5-122">The following example demonstrates how to add and retrieve custom data from a <xref:System.Windows.Ink.StrokeCollection>.</span></span>  
  
 [!code-csharp[HowToAddCustomDataToInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 <span data-ttu-id="ab2a5-123">下面的示例创建的应用程序显示<xref:System.Windows.Controls.InkCanvas>和两个按钮。</span><span class="sxs-lookup"><span data-stu-id="ab2a5-123">The following example creates an application that displays an <xref:System.Windows.Controls.InkCanvas> and two buttons.</span></span>  <span data-ttu-id="ab2a5-124">此按钮时， `switchAuthor`，使两个钢笔用于两个不同的作者。</span><span class="sxs-lookup"><span data-stu-id="ab2a5-124">The button, `switchAuthor`, enables two pens to be used by two different authors.</span></span>  <span data-ttu-id="ab2a5-125">按钮`changePenColors`上的更改每个笔画颜色<xref:System.Windows.Controls.InkCanvas>根据作者。</span><span class="sxs-lookup"><span data-stu-id="ab2a5-125">The button `changePenColors` changes the color of each stroke on the <xref:System.Windows.Controls.InkCanvas> according to the author.</span></span>  <span data-ttu-id="ab2a5-126">应用程序定义了两个<xref:System.Windows.Ink.DrawingAttributes>对象，并将自定义属性添加到指示哪个作者绘制每个<xref:System.Windows.Ink.Stroke>。</span><span class="sxs-lookup"><span data-stu-id="ab2a5-126">The application defines two <xref:System.Windows.Ink.DrawingAttributes> objects and adds a custom property to each one that indicates which author drew the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="ab2a5-127">当用户单击`changePenColors`，应用程序更改根据自定义属性的值的笔划的外观。</span><span class="sxs-lookup"><span data-stu-id="ab2a5-127">When the user clicks `changePenColors`, the application changes the appearance of the stroke according to the value of the custom property.</span></span>  
  
 [!code-xaml[HowToAddCustomDataToInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
